# Distribution

This project does not use `electron-builder`, but the same APFS-vs-HFS+ notarization issue can still matter when you package a DMG on Apple Silicon.

To keep the DMG notarization flow reliable, use the included packaging script. It always creates the staging disk image as `HFS+`, converts it into the final compressed DMG, signs that DMG with the same `Developer ID Application` identity as the app bundle, and can optionally notarize and staple it.

## Create A Release Archive

Archive the macOS app bundle into a predictable local output path:

```bash
xcodebuild \
  -project OneScreen.xcodeproj \
  -scheme OneScreen \
  -configuration Release \
  -archivePath build/archive/OneScreen.xcarchive \
  archive
```

The resulting signed app bundle will be:

```text
build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app
```

For actual distribution, archive with your `Developer ID Application` signing identity enabled. The plain `xcodebuild build` product can retain local debugging entitlements such as `get-task-allow`, which isn't suitable for direct distribution.

## Package The DMG

Create a signed DMG without notarizing it:

```bash
./scripts/package-macos-dmg.sh \
  --app build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app \
  --output dist/OneScreen.dmg \
  --overwrite
```

Create, sign, notarize, and staple the DMG in one step:

```bash
./scripts/package-macos-dmg.sh \
  --app build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app \
  --output dist/OneScreen.dmg \
  --notary-profile onescreen-notary \
  --overwrite
```

## Store Notary Credentials

If you have not created a `notarytool` keychain profile yet, store it once and then reuse that profile name with the script:

```bash
xcrun notarytool store-credentials "onescreen-notary"
```

`notarytool` will prompt for whichever authentication details you choose to use.

## Verify The Final Download

After packaging, you can confirm the app bundle is distribution-safe and the DMG container is signed:

```bash
codesign -dvv build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app 2>&1 | rg "Authority=|TeamIdentifier=|Timestamp="
codesign -d --entitlements :- build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app 2>/dev/null | plutil -p -
spctl -a -vv -t exec build/archive/OneScreen.xcarchive/Products/Applications/OneScreen.app
codesign -dvv dist/OneScreen.dmg 2>&1 | rg "Authority=|TeamIdentifier=|Timestamp=|Notarization Ticket="
```

The app assessment should report `source=Notarized Developer ID`, and the DMG codesign details should show the same `Developer ID Application` authority plus a stapled notarization ticket.

If you want to verify the downloaded execution path, mount the DMG and assess the app inside it:

```bash
mount_dir=$(mktemp -d /tmp/onescreen-dmg-check.XXXXXX)
device=$(hdiutil attach -readonly -noverify -noautoopen -mountpoint "$mount_dir" dist/OneScreen.dmg | awk '/^\/dev\// { print $1; exit }')
spctl -a -vv -t exec "$mount_dir/OneScreen.app"
hdiutil detach "$device"
rmdir "$mount_dir"
```

## Why This Works

The release script explicitly creates the staging DMG with:

```bash
hdiutil create -size ... -fs HFS+ -volname "OneScreen" ...
```

That avoids the APFS DMG default that can leave notarization stuck in `In Progress` indefinitely on Apple Silicon packaging machines.
