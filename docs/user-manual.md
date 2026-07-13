# OneScreen User Manual

OneScreen is a macOS menu bar app that streams a display from your Mac to OneScreen for iPad over your local network. This manual walks through the app in the same order most people use it: setup first, then streaming, then receiver controls and settings.

## What You Need

- A Mac running OneScreen
- An iPad running OneScreen for iPad
- Both devices on the same local network
- NDI Tools installed on the Mac when you plan to stream over NDI; the built-in HEVC engine (beta) does not require it
- Screen Recording enabled for OneScreen on the Mac
- Optional: Accessibility access if you want Keep Cursor Off Display, full screen helpers, or window placement
- Optional: Capture One Automation if you want remote Capture One controls from iPad

## 1. Launch OneScreen

1. Open OneScreen on your Mac.
2. Look for the OneScreen icon in the macOS menu bar.
3. Click the menu bar icon to open the main control panel.
4. If the Welcome to OneScreen setup sheet appears, complete the next section before trying to start a stream.

OneScreen is a menu bar app, so closing the panel does not quit it. Use the `Quit` button in the footer when you want to fully exit the app. By default, OneScreen stays out of the Dock and may also stay out of the macOS Force Quit Applications window. To show it in both places while it is running, turn on `Settings > General > Show Icon in Dock`.

## 2. Complete First-Time Setup

When OneScreen opens for the first time, it shows a setup sheet. It starts with a short intro; click `Set Up Permissions` to reach the checklist of items OneScreen needs before it can stream correctly.

1. Grant `Screen Recording`.
2. Install `NDI Tools for Mac` to satisfy the `NDI Runtime` item. A fresh install streams over NDI by default; if you switch to the HEVC engine later, the NDI runtime is no longer required.
3. Ask macOS for `Local Network` access, then confirm it in System Settings if your iPad cannot find this Mac.
4. Treat `Accessibility` as optional for now unless you already know you want Keep Cursor Off Display, full screen helpers, or window placement.
5. Click `Refresh` after each setup step.
6. If OneScreen suggests a relaunch, click `Relaunch`.
7. Click `Done` when the required items show as complete.

If `Crash Reports` appears, it is optional. Leaving it off does not block setup, and you can change it later in `Settings > Help`.

### What each setup item does

- `Screen Recording`: lets OneScreen detect and stream your displays.
- `NDI Runtime`: provides the runtime OneScreen uses only when the selected engine is NDI. It is marked satisfied automatically when the HEVC engine is selected.
- `Local Network`: lets the Mac discover iPads and publish streams on your network. macOS keeps the final allow or deny choice in System Settings.
- `Accessibility`: enables Keep Cursor Off Display and some window placement/full screen helpers.

### Privacy and network basics

OneScreen captures the display you choose only while streaming or previewing. The live video stream is sent over your local network using the selected NDI or HEVC engine and is not uploaded to Spot Digital servers.

`Open Stream` is discoverable on the local network. `Private Stream` requires QR code or manual passphrase pairing (on NDI it also uses a random NDI group for the session), but it should still be used on trusted networks.

License checks, update checks, and user-triggered feedback may contact online services. See the [Privacy Policy](privacy.md) for details.

## 3. Get Familiar with the Main Control Panel

The menu bar panel is the center of the app. It is organized into a few main areas:

- `Choose a display to stream`: use an existing display or create an iPad-sized virtual display.
- `Preview`: shows a live preview while streaming.
- `Receivers`: shows connected iPads and their controls.
- Footer buttons: `Settings`, `About OneScreen` or `Check for Updates`, and `Quit`, next to the main `Start`/`Stop` button.

If OneScreen shows a red warning instead of a Start button, fix that warning first. The app will not start streaming until the required setup is complete.

## 4. Choose What to Stream

1. Open the picker in the `Choose a display to stream` area.
2. Choose a preset under `Virtual iPad Display` so OneScreen can create a virtual display when streaming starts, or choose a current Mac display under `Existing Displays`.
3. If OneScreen opens a submenu for that iPad size, choose what should appear on the virtual display:
   - Under `Choose a Window`, pick `Capture One Viewer`, a `Client Viewer`, or `Current App Window` to put a window there.
   - Under `Or Leave It Empty`, pick `Empty Display` to create the virtual display without moving a window onto it.
4. If needed, turn on `Keep Window Full Screen` so OneScreen keeps the chosen window filling the streamed display: macOS full screen for the Capture One Viewer, or a fitted capture without toolbar or title bar for Client Viewer windows.
5. Optionally turn on `Keep Cursor Off Display` so the macOS pointer stays off the streamed display. This needs Accessibility access.

While a stream is live, the same two toggles are available from the gear `Stream behavior options` menu.

### When to use an existing Mac display

Use the virtual display workflow when you want the iPad to behave like a dedicated presentation output. If you need to stream one of your current Mac displays instead, choose it from the `Existing Displays` section at the bottom of the display picker.

## 5. Choose Open or Private Streaming

Before you start the stream, decide how the iPad should join it.

### Open Stream

Use the open mode when anyone on the same network may discover and join the stream.

- Leave the lock control in its open state.
- Start the stream.
- Join it from OneScreen for iPad on the same network.

### Private Stream

Use private mode when you want the iPad to join with a one-time pairing code instead of open discovery.

1. Click the lock control so Private Stream is armed.
2. Start the stream.
3. Click the QR code button that appears beside the lock.
4. On the iPad, scan the QR code or enter the manual passphrase.
5. If the code expires, click `Refresh` to generate a new one. Pairing codes expire after about two minutes by design.

If you switch between Open and Private while already streaming, OneScreen asks you to confirm and then restarts the current stream so the new access mode takes effect.

## 6. Start Your First Stream

1. Make sure a virtual iPad display preset or an existing display is selected.
2. Confirm Screen Recording is granted. If the Streaming Engine is NDI, also confirm NDI Tools is installed.
3. Click `Start`.
4. Wait for the status area to move from startup into a live state.
5. Watch the preview area to confirm the correct display is being sent.

While streaming, the status row shows the current engine badge (`NDI` or `HEVC`) and can show live status such as:

- `streaming`
- `paused`
- `intermission`
- `reconnecting`
- `rotating display`

Receiver connections show up in the `Receivers` section rather than in the status text.

If you need to change the selected display, streaming engine, quality, or color space, stop the stream first, make the change, then start again. Stream settings lock while a stream is live, and a banner in Settings explains that.

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
2. Click `Go Live` to go back to the stream.

### Full Screen

1. Hover over the preview and click the corner button to make the current target window full screen on the streamed display. For Client Viewer windows the same corner button fills the screen with the image by hiding the window chrome instead.
2. The `Full Screen` hotkey triggers the same action. Use `Keep Window Full Screen` if you want OneScreen to keep the window that way for the whole stream.

### Lock and Unlock Receiver Controls

1. Click `Lock` to prevent connected iPads from using receiver controls.
2. Click `Unlock` to allow them again.

### Rotate

If the rotate button appears near the preview header, OneScreen can recreate the current virtual iPad display in portrait or landscape (`Rotate 90°` and `Reset Rotation`). Rotation is disabled for the main Mac display.

## 9. Manage Connected Receivers

Each connected iPad receiver gets its own row in the `Receivers` section. The Receivers header also has a button to open the same controls in a floating window.

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
3. Choose a `Profile` if the receiver has saved white balance presets.
4. Use `Reset Profile` to clear the display profile adjustment.

### Framelines

1. Open the same slider panel to turn `Framelines` on or off for that iPad.
2. Use the framelines button in the Receivers header to show or hide framelines at once on every connected iPad that has Framelines enabled.

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

If `Power Save` is enabled in Settings, a leaf button appears in the Receivers header.

1. Click the leaf to dim all connected iPads to the saved Power Save brightness.
2. Click it again to restore each iPad's previous brightness.

## 10. Rate and Review Captures from the iPad

If you use Capture One, OneScreen for iPad can do more than view the stream. With `Capture One Controls` unlocked on the iPad and `Settings > Integrations > Capture One Controls` turned on on the Mac, the iPad live viewer gains navigation, rating, and tagging controls. The Mac always decides which of those controls are available.

### Review sweep in the live viewer

1. On the iPad, turn on the `Previous/Next Buttons` and `Review Buttons` viewer settings.
2. Tap `Review` under a navigation chevron to auto-step through captures in that direction.
3. While the sweep runs, a floating cluster at the bottom of the live view offers `Stop` to end the sweep and `Reverse` to flip its direction.
4. When a sweep ends, `Last Frame` appears briefly so you can jump to the newest capture.
5. Pick the pace with the iPad's `Review Speed` setting: `Slow`, `Normal`, or `Fast` (about 2, 1.2, or 0.6 seconds per capture).

The sweep stops on its own when it reaches the beginning or end of the folder.

### Control Deck

Control Deck turns the iPad into a control surface beside your primary monitor to rate, tag, and review captures — for example when the iPad is mounted under a set monitor.

1. Tap the Control Deck button in the iPad live viewer's toolbar. A black deck replaces the live image.
2. Work the selected capture from the deck:
   - Set star ratings (clear, or 1–5) and color tags.
   - Step between captures with the previous/next buttons, a swipe on the preview, or the same `Review`, `Reverse`, `Stop`, and `Last Frame` sweep controls.
   - Watch the embedded preview thumbnail — it is true live video, not a snapshot — with the capture's file name below it.
   - Read the per-shot plate showing `SHUTTER`, `APERTURE`, `ISO`, and `FOCAL`.
   - Use the Capture One toolbar buttons the Mac allows, such as `Camera`, `AirDrop`, `Live View`, `Before/After`, `Clear Compare`, `Overlay`, `Grid`, `Rotate Left`, and `Rotate Right`.
3. Use the deck's top bar to mute feedback sounds, lock controls, dim the deck to cut glare on set, or open help.
4. Tap `Return to Fullscreen` or the exit button to go back to the live viewer.

Both the review sweep and the Control Deck are part of the paid `Capture One Controls` unlock on the iPad.

## 11. Open the Floating Preview Window

OneScreen has both an in-panel preview and an optional floating Preview Window.

You can open the floating Preview Window in any of these ways:

1. Open `Settings > Preview` and click `Open Preview Window`.
2. Click the preview title pill in the panel's preview header.
3. Press the `Preview` hotkey if you assigned one.

The preview header can also show a display-position badge such as `Left of desktop`. It indicates where the streamed display sits relative to your desktop, and you can hide it with the `Display Location Badge` setting.

The floating Preview Window can be configured to stay on top, close when clicked, pause the stream while it is open, temporarily pause Keep Cursor Off Display, and use a custom opacity.

## 12. Walk Through the Settings Tabs

Open Settings from the gear button in the footer. The main tabs come first; the utility tabs `Updates`, `About`, and `Help` sit below a divider in the sidebar.

### General

App-level behavior:

- `Open at Login`: opens OneScreen when you sign in
- `Show Icon in Dock`: shows OneScreen in the Dock, app switcher, and Force Quit window

### Stream

Everything about the stream itself. While a stream is live these settings lock, and a banner explains that; stop the stream to edit them.

- `Stream Name`: the name iPads see. Applies next time streaming starts.
- `Streaming Engine`: NDI or HEVC (Beta), independent of quality. NDI works with other NDI apps and requires NDI Tools; HEVC is built into macOS with nothing to install and streams at a fixed data rate. Each engine remembers its own quality selection.
- `Quality`: Maximum, High, Balanced, Limited Network, or Custom. The caption under the menu shows the exact size, frame rate, and (for HEVC) data rate.
- `Advanced`: `Stream Size` is a percentage of the streamed display (100 / 75 / 66 / 50 / 33%); `Frame Rate` picks exact fps; HEVC adds a 20–120 Mbps `Data Rate` slider and an 8-bit/10-bit `Bit Depth` preference. Editing any of these sets Quality to Custom.
- `Color Space`: Capture Default, Standard sRGB, Adobe RGB (1998), or Display P3. A previously saved space outside this list stays selectable until changed.
- `Stream Info`: the strip at the foot of the card showing exactly what will be sent — size, fps, engine, data rate, and bit depth (NDI reports `auto rate · 8-bit`). A green dot pulses while live.
- `Streaming Behavior`: `Auto-Start Stream` (with `Use Private Stream` pairing), and `Auto-Switch Displays` if the streamed display disappears.
- `Virtual iPad Display`: `Scale` chooses Retina (HiDPI) or Actual Size for virtual displays.

### Receivers

Use this tab to shape the iPad experience:

- Create `Receiver Name Presets`
- Show or hide display rotation on connected iPads (`Show Display Rotation on iPad`)
- Enable and tune `Power Save`
- Choose how each receiver's battery appears in the menu (`Battery Display`)
- Turn `Battery Low or Not Charging`, `Receiver Goes Offline`, and `Stream Tries to Recover` on or off

### Permissions

Use this tab to review setup and fix missing access:

- Refresh Screen Recording, NDI, and Accessibility status
- Review Capture One AppleScript and Automation status

### Integrations

Use this tab for optional Mac-side integrations:

- Turn `Capture One Controls` on or off
- Decide which Capture One controls are allowed from iPad: `Selection and Camera Controls` (Navigation, Ratings, Color Tags, Camera Controls) and `Toolbar Buttons` (AirDrop, Live View, Before/After, Clear Compare, Overlay, Grid, Rotate Left, Rotate Right)
- Review or change the Capture One target app bundle

### Preview

Use this tab to tune the floating Preview Window:

- `Always on Top`
- `Pause Keep Cursor Off Display While Open`
- `Pause Stream While Open`
- `Click to Close`
- `Warn if Keep Window Full Screen is on`
- `Opacity` and `Display Location Badge`

### Intermission

Use this tab to build the card shown during intermission:

- `Logo + Text`
- `Title Card Image`
- `Solid Color`
- Logo placement, scale, colors, title, subtitle, and preview

### Hotkeys

`Show Hotkeys on Buttons` shows the assigned shortcuts on the menu bar control buttons. Use the `Shortcuts` list to assign keys for:

- `Pause / Resume`
- `Intermission`
- `Preview`
- `Full Screen`
- `Lock Controls`
- `Power Save`
- `Framelines`

### License

Use this tab to:

- Enter or revalidate a license key
- See trial and activation status
- Buy OneScreen for Mac, or deactivate this Mac to move the license

### Updates

- `Automatically Check for Updates`: let OneScreen look for new releases on its own
- `Check for Update Now`: run the Sparkle update flow immediately

### About

App identity in one place: version and build, developer links, the OneScreen for iPad TestFlight beta link, and attributions.

### Help

- `Contact Support`: opens the support flow and includes diagnostics
- `Crash Reports` and `Detailed Diagnostic Logging` toggles, plus quick access to `Diagnostic Logs`
- Links to the `User Manual`, `Privacy Policy`, and `NDI Tools`, with shortcuts back to `Permissions` and `License`

## 13. Update, Get Help, or Quit

Use the footer buttons in the menu bar panel for app-level actions:

- `Settings`: opens the full settings window
- `About OneScreen`: app info (this button offers `Check for Updates` when an update is waiting)
- `Quit`: fully exits OneScreen

Feedback and support live in `Settings > Help > Contact Support`, and the update flow lives in `Settings > Updates`.

If you want OneScreen to appear in the Dock, app switcher, and macOS Force Quit Applications window while it is running, open `Settings > General` and turn on `Show Icon in Dock`.

If OneScreen becomes unresponsive and the footer `Quit` button does not work, use `Activity Monitor`, select `OneScreen`, click the stop button, then choose `Force Quit`. You can also use Terminal:

```bash
killall OneScreen
```

If the process is still stuck, use:

```bash
killall -9 OneScreen
```

Force quitting can interrupt cleanup work, so use it only when the app does not respond to the normal `Quit` button.

## Common Problems

### OneScreen is unresponsive and will not quit

If `Show Icon in Dock` is enabled, open the macOS Force Quit Applications window, select `OneScreen`, then click `Force Quit`. If OneScreen is not listed there, open `Activity Monitor`, select `OneScreen`, click the stop button, then choose `Force Quit`. If needed, use the Terminal commands in [Update, Get Help, or Quit](#13-update-get-help-or-quit).

### OneScreen says no displays are available

Grant `Screen Recording`, then relaunch OneScreen.

### The Start button is disabled

Check all of the following:

1. A virtual iPad display preset or an existing display is selected.
2. Screen Recording is granted.
3. If the selected engine is NDI, NDI Tools is installed.
4. The stream name is not empty.

### Private pairing stops working

Open the QR code panel again and click `Refresh`. Private pairing codes expire quickly by design.

### Keep Cursor Off Display will not turn on

Grant `Accessibility` first. This is separate from Capture One Automation. Depending on your macOS setup, you may also be prompted later for Input Monitoring or pointer-control related permissions.

### Capture One controls are unavailable

Check these items:

1. `Settings > Integrations > Capture One Controls` is turned on.
2. Capture One is running.
3. `Settings > Permissions > Capture One` shows a good AppleScript and Automation state. Accessibility only affects window placement/full screen helpers.
4. The correct Capture One app bundle is selected if you have multiple installs.
5. On the iPad, `Capture One Controls` is unlocked — the review sweep and Control Deck only appear with the unlock in place.

## Suggested Daily Workflow

1. Launch OneScreen from the menu bar.
2. Select a virtual iPad display preset.
3. Choose Open or Private streaming.
4. Click `Start`.
5. Join from the iPad.
6. Use Pause, Intermission, Full Screen, and receiver controls as needed.
7. Open Settings only when you want to tune behavior or configure optional features.

This manual is a first-pass walkthrough for the current macOS app flow. The next logical upgrade is a screenshot version that matches each step to the exact UI.
