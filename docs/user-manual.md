# OneScreen User Manual

OneScreen is a macOS menu bar app that streams a display from your Mac to OneScreen for iPad over your local network. This manual walks through the app in the same order most people use it: setup first, then streaming, then receiver controls and settings.

It describes OneScreen 1.0.3 (55).

## What You Need

- A Mac running OneScreen (macOS 14.0 or later)
- An iPad running OneScreen for iPad
- Both devices on the same local network
- Screen Recording enabled for OneScreen on the Mac
- Accessibility access for Keep Cursor Off Display, full screen helpers, and window placement
- Optional: NDI Tools, and only if you switch the streaming engine to NDI. HEVC is the default and needs nothing installed.
- Optional: Capture One Automation if you want remote Capture One controls from iPad

## 1. Launch OneScreen

1. Open OneScreen on your Mac.
2. Look for the OneScreen icon in the macOS menu bar.
3. Click the menu bar icon to open the main control panel.
4. If the `Welcome to OneScreen for Mac` setup sheet appears, complete the next section before trying to start a stream.

OneScreen is a menu bar app, so closing the panel does not quit it. Use the `Quit` button in the footer when you want to fully exit the app. By default, OneScreen stays out of the Dock and may also stay out of the macOS Force Quit Applications window. To show it in both places while it is running, turn on `Settings > General > Show Icon in Dock`.

## 2. Complete First-Time Setup

When OneScreen opens for the first time it runs a short first-start flow: a welcome screen, then permissions, then a three-slide quickstart tour.

1. On the welcome screen, click `Get Started`.
2. On `Set Up Permissions`, work down the list:
   - Grant `Screen Recording`. This is the one item OneScreen cannot stream without.
   - Grant `Accessibility` for Keep Cursor Off Display, full screen helpers, and window placement.
   - Install `NDI Tools for Mac` only if you plan to use NDI. HEVC is built in and needs no runtime, so you can skip this.
   - Ask macOS for `Local Network` access, then confirm it in System Settings if your iPad cannot find this Mac.
3. Click `Refresh` after granting something in System Settings, so the sheet re-reads the current state.
4. If OneScreen offers `Relaunch`, click it. macOS often keeps reporting the old answer for Screen Recording until the app restarts, and OneScreen returns to the tour afterwards rather than starting over.
5. Click `Continue` to move on to the tour. `Continue` always advances — you can grant anything you skipped later in `Settings > Permissions`.
6. Step through the tour with `Next`, then click `Done`.

`Not Now` closes the flow from any step.

If `Crash Reports` appears below the permission list, it is optional. Leaving it off does not block setup, and you can change it later in `Settings > Help`.

### What each setup item does

- `Screen Recording`: lets OneScreen detect and stream your displays.
- `Accessibility`: enables Keep Cursor Off Display and some window placement/full screen helpers. The sheet marks it Required because those features depend on it, but streaming itself works without it.
- `NDI Tools`: provides the runtime OneScreen uses only when the selected streaming engine is NDI.
- `Local Network`: lets the Mac discover iPads and publish streams on your network. macOS keeps the final allow or deny choice in System Settings, so this item appears only in first-time setup, not in the Permissions tab.

### Privacy and network basics

OneScreen captures the display you choose only while streaming or previewing. The live video stream is sent over your local network using the selected streaming engine and is not uploaded to Spot Digital servers.

`Open Stream` publishes a stream that is discoverable on the local network. `Private Stream` requires QR code or manual passcode pairing. Over HEVC, a private session also encrypts the video itself between this Mac and any receiver that supports encryption, but private mode should still be used on trusted networks.

License checks, update checks, and user-triggered feedback may contact online services. See the [Privacy Policy](privacy.md) for details.

## 3. Get Familiar with the Main Control Panel

The menu bar panel is the center of the app. It is organized into a few main areas:

- `Choose a display to stream`: use an existing display or create an iPad-sized virtual display.
- The lock control beside the display picker: switches between `Open Stream` and `Private Stream`.
- `Preview`: shows a live preview while streaming, with the live controls and a stream-behavior gear below it.
- `Receivers`: shows connected iPads and their controls.
- Footer: `Settings`, `About OneScreen` (this becomes `Check for Updates` when an update is waiting), `Quit`, and the `Start` / `Stop` button.

If OneScreen shows a red warning instead of a Start button, fix that warning first. The app will not start streaming until the required setup is complete.

## 4. Choose What to Stream

1. Open the picker in the `Choose a display to stream` area.
2. Choose a preset under `Virtual iPad Display` so OneScreen can create a virtual display when streaming starts, or choose a current Mac display under `Existing Displays`.
3. Each iPad preset opens a submenu. Choose what should appear on the virtual display:
   - Under `Choose a Window`, pick `Capture One Viewer`, a `Client Viewer`, or `Current App Window` to put a window there.
   - Under `Or Leave It Empty`, pick `Empty Display` to create the virtual display without moving a window onto it.
4. If needed, turn on `Keep Window Full Screen` from the stream-behavior gear so OneScreen tries to keep the chosen window full screen on the virtual display while streaming.

### When to use an existing Mac display

Use the virtual display workflow when you want the iPad to behave like a dedicated presentation output. If you need to stream one of your current Mac displays instead, choose it from the `Existing Displays` section at the bottom of the display picker.

## 5. Choose Open or Private Streaming

Before you start the stream, decide how the iPad should join it.

### Open Stream

Use the open mode when you want the stream to be discoverable on the local network.

- Leave the lock control in its open state.
- Start the stream.
- Join it from OneScreen for iPad on the same network.

### Private Stream

Use private mode when you want the iPad to join with a one-time pairing code instead of open discovery.

1. Click the lock control so Private Stream is armed.
2. Start the stream.
3. Click the QR code button that appears beside the lock.
4. On the iPad, scan the QR code or enter the `Manual Passcode`.
5. If the code expires, click `Refresh` to generate a new one.

Click the expand button on the QR panel to show the code full screen for an iPad across the room. Click anywhere or press `Esc` to close it.

If you switch between Open and Private while already streaming, OneScreen asks you to confirm and then restarts the current stream so the new access mode takes effect.

## 6. Start Your First Stream

1. Make sure a display or virtual iPad display preset is selected.
2. Confirm Screen Recording is set up. If `Settings > Stream > Streaming Engine` is set to NDI, also confirm NDI Tools is installed.
3. Click `Start`.
4. Wait for the status area to move from startup into a live state.
5. Watch the preview area to confirm the correct display is being sent.

While streaming, the panel can show live status such as:

- `streaming`
- `receiver connected`
- `no receiver`
- `reconnecting`
- `rotating display`

Over HEVC the status pill also shows the measured send rate for the live stream.

OneScreen holds the Mac awake for as long as a stream is running, so the machine will not idle-sleep mid-session and drop every receiver at once. Display sleep still follows your own schedule, and an explicit sleep — closing the lid, or the Apple menu — still wins.

If you need to change the selected display, streaming engine, quality, or color space, stop the stream first, make the change, then start again. Those settings lock while a stream is live and the Stream tab shows a banner explaining why.

## 7. Connect and Use an iPad Receiver

Once the stream is live, connect from OneScreen for iPad.

1. Open OneScreen for iPad.
2. Join the live stream.
3. Return to the Mac and look in the `Receivers` section.
4. When the iPad is recognized as a OneScreen receiver, it appears there with its own controls.

If the Mac sees viewers but not full OneScreen receivers, the panel may show unknown viewers instead of named receivers.

## 8. Use the Live Controls During a Stream

The preview area gives you the main live controls for the current stream. When `Show Hotkeys on Buttons` is on, each button also shows its assigned shortcut.

### Pause and Resume

1. Click `Pause` to freeze the live feed.
2. Click `Resume` to continue the feed.

Pausing affects the main stream.

### Intermission

1. Click `Intermission` to replace the live feed with your configured intermission card.
2. Click `Go Live` to go back to the stream.

### Lock and Unlock Receiver Controls

1. Click `Lock` to prevent connected iPads from using receiver controls.
2. Click `Unlock` to allow them again.

### Stream Behavior Gear

The gear beside the live controls opens a `While Streaming` menu with two toggles:

- `Keep Cursor Off Display`: keeps the pointer from wandering onto the streamed display.
- `Keep Window Full Screen`: keeps the target window full screen on the streamed display.

Both stay available while the stream is live, and each greys out when the current display or window cannot support it.

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
4. Use `Reset` to clear the display profile adjustment, or save the profile and sync it to your other displays.

### Identify a receiver

1. Click the broadcast-style identify button.
2. OneScreen tells that iPad to identify itself so you know which device you are controlling.

### Return a receiver to live view

1. Click the live-view button on a receiver row.
2. OneScreen reopens the live view on that iPad.

The button greys out while that iPad is already in the live view.

### Pause or lock a single receiver

1. Use the play/pause button to pause or resume just that receiver.
2. Use the lock button to lock or unlock just that receiver.

These per-receiver controls are separate from the main stream Pause and Lock controls.

### Read each receiver's connection

With `Connection Quality` on, every receiver row carries a set of signal bars and a subline showing that iPad's live data rate. The bars come from round-trip probes, so they read punctuality rather than raw throughput, and the subline stays quiet until something is worth reporting.

Each row also shows the receiver's battery according to the `Battery Display` setting — as an icon, as a percentage, or not at all.

### Framelines

If the framelines button appears in the `Receivers` header, click it to show or hide framelines on every receiver that has them enabled. The button fills with the accent color while framelines are visible.

### Power Save

If `Power Save` is enabled in Settings, a leaf button appears in the Receivers header.

1. Click the leaf to dim all connected iPads to the saved Power Save brightness.
2. Click it again to restore each iPad's previous brightness.

The button fills with the accent color while Power Save is on.

### Activity banners

When something on an iPad is holding the stream, a banner appears above the receiver list with a one-click way out:

- `Capture One Live View is on` offers `Turn Off`.
- `Review mode is active` offers `Stop`, which ends the review sweep on every reviewing receiver.

## 10. Pop the Receivers List Into Its Own Window

On a busy set the menu bar panel closes every time you click elsewhere. You can move the receiver list into a floating window instead.

1. Click the pop-out button in the `Receivers` header (`Open Receivers in a floating window`).
2. The window carries the same receiver rows, the same activity banners, and a compact stream action strip with `Pause` / `Resume`, `Intermission` / `Go Live`, and `Lock` / `Unlock`.
3. Use the gear in the window's header to open `Window Options` and turn `Always on Top` on or off.
4. Click the close button to put the receivers back in the menu bar panel.

The window sizes itself to its list, and the intermission card is kept off the display the Receivers window is on so the window stays usable during an intermission.

## 11. Open the Floating Preview Window

OneScreen has both an in-panel preview and an optional floating Preview Window.

You can open the floating Preview Window in either of these ways:

1. Open `Settings > Preview` and click the Preview Window button.
2. If the preview header shows a display-position badge such as `Left of desktop`, click that badge.

The floating Preview Window can be configured to stay on top, close when clicked, pause the stream while it is open, and temporarily suspend Keep Cursor Off Display while it is open.

## 12. Walk Through the Settings Tabs

Open Settings from the gear button in the footer. The sidebar lists nine main tabs — General, Stream, Receivers, Integrations, Preview, Intermission, Hotkeys, Permissions, and License — plus Updates, About, and Help below them.

### General

App-level behavior:

- `Open at Login`: opens OneScreen when you sign in
- `Show Icon in Dock`: shows OneScreen in the Dock, app switcher, and Force Quit window

### Stream

Everything about the stream itself. While a stream is live these settings lock, and a banner explains that; stop the stream to edit them.

- `Stream Name`: the name iPads see. Applies next time streaming starts.
- `Streaming Engine`: HEVC or NDI, independent of quality. HEVC is the default, is built into macOS with nothing to install, and streams at a fixed data rate. NDI works with other NDI apps and requires NDI Tools. Each engine remembers its own quality selection.
- `Quality`: Maximum, High, Balanced, Limited Network, or Custom. The caption under the menu shows the exact size, frame rate, and (for HEVC) data rate.
- `Advanced`: `Stream Size` is a percentage of the streamed display (200 / 150 / 100 / 75 / 66 / 50 / 33%, with 150% and 200% offered only for a virtual iPad display, where they create real extra HiDPI pixels for clearer zooming); `Frame Rate` picks exact fps (60 / 30 / 20 / 15 / 10 / 8 / 5); HEVC adds a 20–120 Mbps `Data Rate` slider and an 8-bit/10-bit `Bit Depth` preference. Editing any of these sets Quality to Custom.
- `Color Space`: Capture Default, Standard sRGB, Adobe RGB (1998), Display P3, or ITU-R BT.709. A previously saved space outside this list stays selectable until changed.
- `Stream Info`: the strip at the foot of the card showing exactly what will be sent — size, fps, engine, data rate, and bit depth (NDI reports `auto rate · 8-bit`). A green dot pulses while live.
- `Streaming Behavior`: `Auto-Start Stream` (with `Use Private Stream` pairing), and `Auto-Switch Displays` if the streamed display disappears.
- `Virtual iPad Display`:
  - `Scale` chooses Retina (HiDPI) or Actual Size for virtual displays.
  - `Default Display Placement` chooses which side of the desktop a new virtual display is created on.
  - `Start Stream in Vertical Orientation` creates the virtual iPad display in portrait when the stream starts.
  - `Keep Other Windows off the Display` moves stray windows that land on the virtual display back to the main display.

### Receivers

Use this tab to shape the iPad experience:

- Create `Name Presets` for fast receiver renaming
- `Show Display Rotation on iPad` adds the rotation button to the iPad viewer when this Mac can rotate the selected display
- Enable and tune `Power Save`
- `Battery Display` shows each receiver's battery as an icon, as a percentage, or not at all
- `Connection Quality` shows each iPad's signal strength and live data rate in the receivers list while streaming
- Turn `Battery Low or Not Charging`, `Receiver Goes Offline`, and `Stream Tries to Recover` on or off

### Integrations

Use this tab for optional Mac-side integrations:

- Turn `Capture One Controls` on or off
- Decide which controls are allowed from iPad, under `Selection and Camera Controls` (Navigation, Ratings, Color Tags, Camera Controls, AirDrop, Live View) and `Toolbar Buttons` (Clear Compare, Before/After, Overlay, Grid, Guides, Rotate Left, Rotate Right)
- Review or change the Capture One target app bundle

### Preview

Use this tab to tune the floating Preview Window.

`Behavior`:

- `Always on Top`
- `Pause Keep Cursor Off Display While Open`
- `Pause Stream While Open`
- `Click to Close`
- `Warn if Keep Window Full Screen is on`

`Appearance`:

- `Opacity`
- `Display Location Badge`

### Intermission

Use this tab to build the card shown during intermission:

- `Mode`: `Logo + Text`, `Title Card Image`, or `Solid Color`
- `Secondary Displays`: also show the card full screen on every connected display except the main display
- Logo placement, scale, colors, title, subtitle, and preview

Click `Test` beside the preview to check the card at full size before a shoot. The
test covers every display except the one you are working on, so your main screen
stays usable, and the button becomes `End Test` while it is showing. On a
single-display Mac the test takes over the current screen instead and ends on any
click or key press.

The test is local to your Mac. It never touches the stream, your receivers, or a
real intermission already in progress, and it is excluded from capture so it
cannot appear in a running stream. It clears itself automatically if you leave it
up, and it stays disabled until you have configured a card.

### Hotkeys

`Show Hotkeys on Buttons` puts each shortcut on its menu bar control button.

Assign keyboard shortcuts for:

- Pause / Resume
- Intermission
- Preview
- Full Screen
- Lock Controls
- Power Save
- Framelines
- Recall Mouse Pointer to Main Display

### Permissions

Use this tab to review setup and fix missing access:

- Refresh `Screen Recording`, `Accessibility`, and `NDI Runtime (Optional)` status
- Review Capture One AppleScript and Automation status

Local Network access is asked for during first-time setup rather than here, because macOS keeps the final allow or deny choice in System Settings.

### License

Use this tab to:

- Enter or revalidate a license key
- See trial and activation status
- Open checkout if your build exposes purchasing

### Updates

- `Automatically Check for Updates`
- `Check for Update Now`

### About

App version and developer details, the OneScreen for iPad App Store link with a QR code you can scan with your iPad's camera, and attributions. Click the QR code to show it full screen; click anywhere or press Esc to close it.

### Help

- `Contact Support` opens the support form and copies a redacted app summary to your clipboard
- `Crash Reports` turns optional crash reporting on or off
- `Detailed Diagnostic Logging` records extra stream and display detail for support; it takes effect after a relaunch
- `Diagnostic Logs` exports a local zip of logs if support asks for one
- `User Manual`, `Privacy Policy`, and `NDI Tools` links
- Shortcuts back to the `Permissions` and `License` tabs

## 13. Update, Get Help, or Quit

Use the footer buttons in the menu bar panel for app-level actions:

- `Settings`: opens the full settings window
- `About OneScreen`: app info. This button becomes `Check for Updates` when an update is waiting.
- `Quit`: fully exits OneScreen

To send feedback, open `Settings > Help` and use `Contact Support`.

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

1. A display or virtual iPad display preset is selected.
2. Screen Recording is granted.
3. If the selected streaming engine is NDI, NDI Tools is installed.
4. The stream name is not empty.

### The iPad cannot find this Mac

Confirm both devices are on the same network, then confirm Local Network access for OneScreen in System Settings. macOS ties that grant to the exact binary, so a fresh install or update can need it again.

### Private pairing stops working

Open the QR code panel again and click `Refresh`. Private pairing codes expire quickly by design.

### Keep Cursor Off Display will not turn on

Grant `Accessibility` first. This is separate from Capture One Automation. Depending on your macOS setup, you may also be prompted later for Input Monitoring or pointer-control related permissions.

When Keep Cursor Off Display is on, OneScreen also runs an automatic backup recovery path — there is nothing to configure. If macOS still reports the pointer on the streamed display, the Preview Window is closed, and there has been no mouse activity for five seconds, OneScreen moves the pointer to the center of the main display by itself. To bring the pointer back on demand at any time, assign the `Recall Mouse Pointer to Main Display` hotkey.

### An iPad shows weak signal or a stuttering picture

Turn on `Settings > Receivers > Connection Quality` and watch that receiver's bars and data-rate subline. If the bars drop on a busy network, lower `Quality` — or, under `Advanced`, lower `Data Rate` or `Frame Rate` — and start the stream again.

### Capture One controls are unavailable

Check these items:

1. `Settings > Integrations > Capture One Controls` is turned on.
2. Capture One is running.
3. `Settings > Permissions > Capture One` shows a good AppleScript and Automation state. Accessibility only affects window placement/full screen helpers.
4. The correct Capture One app bundle is selected if you have multiple installs.

## Suggested Daily Workflow

1. Launch OneScreen from the menu bar.
2. Select a display or virtual iPad display preset.
3. Choose Open or Private streaming.
4. Click `Start`.
5. Join from the iPad.
6. Pop the Receivers list into its own window if you will be working away from the menu bar.
7. Use Pause, Intermission, and receiver controls as needed.
8. Open Settings only when you want to tune behavior or configure optional features.

This manual is a first-pass walkthrough for the current macOS app flow. The next logical upgrade is a screenshot version that matches each step to the exact UI.
