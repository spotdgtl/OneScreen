# OneScreen User Manual

OneScreen is a macOS menu bar app that streams a display from your Mac to OneScreen for iPad over your local network. This manual walks through the app in the same order most people use it: setup first, then streaming, then receiver controls and settings.

## What You Need

- A Mac running OneScreen
- An iPad running OneScreen for iPad
- Both devices on the same local network
- NDI Tools installed on the Mac
- Screen Recording enabled for OneScreen on the Mac
- Optional: Accessibility access if you want Cursor Lock or fullscreen window helpers
- Optional: Capture One if you want remote Capture One controls from iPad

## 1. Launch OneScreen

1. Open OneScreen on your Mac.
2. Look for the OneScreen icon in the macOS menu bar.
3. Click the menu bar icon to open the main control panel.
4. If the Welcome to OneScreen setup sheet appears, complete the next section before trying to start a stream.

OneScreen is a menu bar app, so closing the panel does not quit it. Use the `Quit` button in the footer when you want to fully exit the app.

## 2. Complete First-Time Setup

When OneScreen opens for the first time, it shows a setup sheet with the items it needs before it can stream correctly.

1. Grant `Screen Recording`.
2. Install `NDI Tools for Mac`.
3. Allow `Local Network` access when macOS prompts you.
4. Treat `Accessibility` as optional for now unless you already know you want Cursor Lock or fullscreen helpers.
5. Click `Refresh Status` after each setup step.
6. If OneScreen suggests a relaunch, click `Relaunch OneScreen`.
7. Click `Done` when the required items show as complete.

### What each setup item does

- `Screen Recording`: lets OneScreen detect and stream your displays.
- `NDI Tools`: provides the NDI runtime OneScreen uses to publish video.
- `Local Network`: lets the Mac discover iPads and publish streams on your network.
- `Accessibility`: enables Cursor Lock and some window-targeting/fullscreen helpers.

### Privacy and network basics

OneScreen captures the display you choose only while streaming or previewing. The live video stream is sent over your local network using NDI and is not uploaded to Spot Digital servers.

`Open NDI` publishes a discoverable local NDI source. `Private Stream` requires QR code or manual passphrase pairing and uses a random NDI group for the session, but it should still be used on trusted networks.

License checks, update checks, and user-triggered feedback may contact online services. See [Privacy & Network Notes](privacy.md) for details.

## 3. Get Familiar with the Main Control Panel

The menu bar panel is the center of the app. It is organized into a few main areas:

- `Status / Select a display to stream`: choose what the Mac should stream.
- `Preview`: shows a live preview while streaming.
- `Receivers`: shows connected iPads and their controls.
- Footer buttons: `About`, `Check for Updates`, `Send Feedback`, `Settings`, and `Quit`.

If OneScreen shows a red warning instead of a Start button, fix that warning first. The app will not start streaming until the required setup is complete.

## 4. Choose What to Stream

1. Open the display picker in the `Select a display to stream` area.
2. Choose one of your current Mac displays if you want to stream an existing screen.
3. Or choose a preset under `Create A Virtual iPad Display` if you want OneScreen to create a virtual display when streaming starts.
4. If OneScreen shows a `Display Source` submenu for that selection, choose the source you want:
   - `As-Is (No Auto-Target)` keeps window targeting off.
   - `Top Window (Frontmost App)` sends the current frontmost window.
   - `Capture One Viewer` or a `Client Viewer` option is for Capture One workflows.
5. If needed, turn on `Maintain Fullscreen` so OneScreen keeps the target window in fullscreen mode while streaming.

### When to use a virtual iPad display

Use a virtual display when you want the iPad to behave like a dedicated presentation output instead of mirroring an existing Mac display. OneScreen creates the selected virtual display when you press `Start`.

## 5. Choose Open or Private Streaming

Before you start the stream, decide how the iPad should join it.

### Open NDI

Use the open mode when you want the stream to be discoverable on the local network.

- Leave the lock control in its open state.
- Start the stream.
- Join it from OneScreen for iPad on the same network.

### Private Stream

Use private mode when you want the iPad to join with a one-time pairing code instead of open discovery.

1. Click the lock control so Private Stream is armed.
2. Start the stream.
3. Click the QR code button that appears beside the lock.
4. On the iPad, scan the QR code or enter the manual passphrase.
5. If the code expires, click `Refresh` to generate a new one.

If you switch between Open and Private while already streaming, OneScreen restarts the current stream so the new access mode takes effect.

## 6. Start Your First Stream

1. Make sure a display or virtual iPad display is selected.
2. Confirm Screen Recording and NDI Tools are already set up.
3. Click `Start`.
4. Wait for the status area to move from startup into a live state.
5. Watch the preview area to confirm the correct display is being sent.

While streaming, the panel can show live status such as:

- `streaming`
- `receiver connected`
- `no receiver`
- `reconnecting`
- `rotating display`

If you need to change the selected display, bandwidth mode, or color profile, stop the stream first, make the change, then start again.

## 7. Connect and Use an iPad Receiver

Once the stream is live, connect from OneScreen for iPad.

1. Open OneScreen for iPad.
2. Join the live stream.
3. Return to the Mac and look in the `Receivers` section.
4. When the iPad is recognized as a OneScreen receiver, it appears there with its own controls.

If the Mac sees viewers but not full OneScreen receivers, the panel may show unknown viewers instead of named receivers.

## 8. Use the Live Controls During a Stream

The preview area gives you the main live controls for the current stream.

### Pause and Resume

1. Click `Pause` to freeze the live feed.
2. Click `Resume` to continue the feed.

Pausing affects the main stream.

### Intermission

1. Click `Intermission` to replace the live feed with your configured intermission card.
2. Click `Resume Live` to go back to the stream.

### Fullscreen

1. Click `Fullscreen` to fullscreen the current target window on the selected display.
2. Use this with `Maintain Fullscreen` if you want OneScreen to keep that window fullscreen while streaming.

### Lock and Unlock Receiver Controls

1. Click `Lock` to prevent connected iPads from using receiver controls.
2. Click `Unlock` to allow them again.

### Rotate

If the rotate button appears near the preview header, OneScreen supports rotating the selected display or recreating the current virtual iPad display in the other orientation.

## 9. Manage Connected Receivers

Each connected iPad receiver gets its own row in the `Receivers` section.

### Rename a receiver

1. Click the receiver name pill.
2. Edit the name directly, or apply one of the saved presets.
3. Confirm the change.

### Change receiver color

1. Click the receiver name pill.
2. Pick a color swatch, or use the custom color picker.

### Adjust brightness and display profile

1. Click the slider button on the receiver row.
2. Use the brightness slider to dim or brighten that iPad.
3. Choose a `Display Profile` if the receiver has saved white balance presets.
4. Use `Reset` to clear the display profile adjustment.

### Identify a receiver

1. Click the broadcast-style identify button.
2. OneScreen tells that iPad to identify itself so you know which device you are controlling.

### Return a receiver to live view

1. Click the live-view button on a receiver row.
2. OneScreen reopens the live view on that iPad.

### Pause or lock a single receiver

1. Use the play/pause button to pause or resume just that receiver.
2. Use the lock button to lock or unlock just that receiver.

These per-receiver controls are separate from the main stream Pause and Lock controls.

### Power Save

If `Power Save` is enabled in Settings, a lightbulb button appears in the Receivers header.

1. Click the lightbulb to dim all connected iPads to the saved Power Save brightness.
2. Click it again to restore each iPad's previous brightness.

## 10. Open the Floating Preview Window

OneScreen has both an in-panel preview and an optional floating Preview Window.

You can open the floating Preview Window in either of these ways:

1. Open `Settings > Preview` and click the Preview Window button.
2. If the preview header shows a display-position badge such as `Left of desktop`, click that badge.

The floating Preview Window can be configured to stay on top, close when clicked, and temporarily suspend Cursor Lock while it is open.

## 11. Walk Through the Settings Tabs

Open Settings from the gear button in the footer.

### Stream

Use this tab to control how the stream behaves before or during setup:

- `Stream Host Name`: the published stream name
- `Bandwidth Mode`: Best, Balanced, Low Bandwidth, or Custom
- `Output Color Space`: choose the capture/output color space
- `Cursor Lock`: keep the cursor off the streamed display
- `Switch Displays Automatically`: choose whether OneScreen should fall back to another display if the selected one disappears

### Receivers

Use this tab to shape the iPad experience:

- Create `Receiver Name Presets`
- Enable and tune `Power Save`
- Turn `Battery Alerts`, `Receiver Offline Alerts`, and `Stream Recovery Alerts` on or off

### Permissions

Use this tab to review setup and fix missing access:

- Refresh Screen Recording, NDI, and Accessibility status
- Reopen Screen Recording or Accessibility settings
- Review Capture One AppleScript and Automation status

### Integrations

Use this tab for optional Mac-side integrations:

- Turn `Capture One Controls` on or off
- Decide which Capture One controls are allowed from iPad
- Review or change the Capture One target app bundle

### Preview

Use this tab to tune the floating Preview Window:

- `Always on Top`
- `Turn Off Cursor Lock During Preview`
- `Close Preview on Click`
- `Warn When Maintain Fullscreen Is On`
- `Opacity`

### Intermission

Use this tab to build the card shown during intermission:

- `Logo + Text`
- `Title Card Image`
- `Solid Color`
- Logo placement, scale, colors, title, subtitle, and preview

### Hotkeys

Use this tab to assign keyboard shortcuts for:

- Pause / Resume
- Intermission
- Preview Window
- Fullscreen Window
- Lock / Unlock Controls
- Power Save On / Off

### License

Use this tab to:

- Enter or revalidate a license key
- See trial and activation status
- Open checkout if your build exposes purchasing

## 12. Update, Get Help, or Quit

Use the footer buttons in the menu bar panel for app-level actions:

- `About`: app info
- `Check for Updates`: Sparkle update flow
- `Send Feedback`: opens the support flow and includes diagnostics
- `Settings`: opens the full settings window
- `Quit`: fully exits OneScreen

## Common Problems

### OneScreen says no displays are available

Grant `Screen Recording`, then relaunch OneScreen.

### The Start button is disabled

Check all of the following:

1. A display or virtual iPad display is selected.
2. Screen Recording is granted.
3. NDI Tools is installed.
4. The stream name is not empty.

### Private pairing stops working

Open the QR code panel again and click `Refresh`. Private pairing codes expire quickly by design.

### Cursor Lock will not turn on

Grant `Accessibility` first. Depending on your macOS setup, you may also be prompted later for Input Monitoring or pointer-control related permissions.

### Capture One controls are unavailable

Check these items:

1. `Settings > Integrations > Capture One Controls` is turned on.
2. Capture One is running.
3. `Settings > Permissions > Capture One Permissions` shows a good AppleScript and Automation state.
4. The correct Capture One app bundle is selected if you have multiple installs.

## Suggested Daily Workflow

1. Launch OneScreen from the menu bar.
2. Select a display or virtual iPad display.
3. Choose Open or Private streaming.
4. Click `Start`.
5. Join from the iPad.
6. Use Pause, Intermission, Fullscreen, and receiver controls as needed.
7. Open Settings only when you want to tune behavior or configure optional features.

This manual is a first-pass walkthrough for the current macOS app flow. The next logical upgrade is a screenshot version that matches each step to the exact UI.
