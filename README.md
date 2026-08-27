# OneScreen for Mac / iPad

<p align="center">
  <img src="docs/images/onescreen-logo.png" alt="OneScreen icon" width="96" />
</p>

<p align="center">
  <a href="https://github.com/spotdgtl/OneScreen/releases/latest"><img src="https://img.shields.io/badge/Download-latest%20release-black?style=for-the-badge&logo=github" alt="Download latest release" height="24" /></a>
  <a href="https://github.com/spotdgtl/OneScreen/releases/latest"><img src="https://img.shields.io/badge/macOS-14.0%2B-1793d1?style=for-the-badge&logo=apple&logoColor=white&labelColor=555555" alt="macOS 14.0 or later" height="24" /></a>
  <img src="https://img.shields.io/badge/HEVC-built%20in-1793d1?style=for-the-badge&labelColor=555555" alt="Built-in HEVC streaming engine" height="24" />
  <a href="https://apps.apple.com/us/app/onescreen-for-ipad/id6761702167"><img src="https://img.shields.io/badge/iPad-App%20Store-0a84ff?style=for-the-badge&logo=appstore&logoColor=white&labelColor=555555" alt="OneScreen for iPad on the App Store" height="24" /></a>
  <img src="https://img.shields.io/badge/Swift-5-F05138?style=for-the-badge&logo=swift&logoColor=white&labelColor=555555" alt="Swift 5" height="24" />
  <a href="https://github.com/spotdgtl/OneScreen/releases/latest"><img src="https://img.shields.io/badge/Apple%20Notarized-%E2%9C%93-4cbb17?style=for-the-badge&logo=apple&logoColor=white&labelColor=555555" alt="Apple notarized" height="24" /></a>

OneScreen is a Mac app that wirelessly streams an existing display or virtual iPad-sized display to the **OneScreen for iPad** companion app over your local network, turning any iPad into a dedicated viewing monitor. It streams over the built-in HEVC engine by default — nothing extra to install — or over NDI when you need compatibility with other NDI apps, plus private pairing, live display controls, and Capture One integration.

## Highlights

- **Create a virtual, iPad-sized display on demand** so you can stream a dedicated workspace instead of mirroring an existing screen — portrait or landscape, Retina or actual size, placed on the side of the desktop you choose.
- **Stream an existing Mac display when needed** for manual capture setups or advanced workflows.
- **Choose your streaming engine** — the built-in HEVC engine is the default, needs nothing installed, and streams at a data rate you set; NDI works with other NDI apps and tools. Each engine remembers its own quality settings.
- **Open or Private stream modes**, with QR code or manual passcode pairing to keep your stream off other receivers on the network. Over HEVC, private sessions also encrypt the video on the wire.
- **Inline stream controls** to pause, resume, trigger an intermission screen, lock the receivers, or rotate the display — plus Keep Cursor Off Display and Keep Window Full Screen from the stream behavior menu.
- **Floating Preview window** that mirrors what the iPad is currently showing, so you don't have to look at the receiver to check the output.
- **Manage connected iPads from the Mac**, including custom names and color labels, brightness, display profile selection and profile sync, framelines control, identify, return-to-live, per-receiver pause, and per-receiver lock.
- **See how every iPad is actually doing** — signal strength and live data rate per receiver, plus battery, right in the receivers list.
- **Pop the receivers list into a floating window** that stays on top and carries its own pause, intermission, and lock controls, so you can work away from the menu bar.
- **One-click exits from anything holding the stream**, with banners for Capture One Live View and iPad review mode.
- **Power Save** dims all of the connected receivers to extend iPad battery life during down time with the press of a button, and restores them on demand.
- **Tune the stream to your network** — quality presets, or a custom stream size, frame rate, 20–120 Mbps data rate, 8-bit or 10-bit depth, and output color space, with a Stream Info strip that always shows exactly what is being sent.
- **Intermission cards** built from a logo plus text, a title card image, or a solid color, optionally mirrored to every secondary display, with a local Test mode for checking the card before a shoot.
- **Automatic display fallback** keeps the stream alive if the source display disconnects — or you can have it terminate cleanly instead.
- **Your Mac stays awake** for as long as a stream is running, so it can't idle-sleep mid-session and drop every receiver at once.
- **Global hotkeys** for pause/resume, intermission, preview window, full screen, lock controls, Power Save, framelines, and recalling the mouse pointer to the main display.
- **Capture One Controls integration** iPad companion actions like navigation, ratings, color tags, camera controls, capture button, AirDrop, Live View, overlays, grid, guides, clear compare, and image rotation toggles.
- **Control Deck** turns the iPad into a control surface beside your primary monitor to rate, tag, and review captures — with a live preview thumbnail and per-shot EXIF and exposure info (part of Capture One Controls).

## Trial and Licensing

OneScreen includes a 3-day free trial with full streaming on each Mac. You can [purchase an early license](https://spotdgtl.lemonsqueezy.com/checkout/buy/d192eedf-4770-4e21-bb20-bfbb37f82aeb?discount=0) to keep using the Mac app after the trial and support development.

If you want to test longer before purchasing, email [graham@spotdgtl.com](mailto:graham@spotdgtl.com) for an extended trial license. License activation, validation, revalidation, and removal are all handled in **Settings > License**.

## OneScreen for iPad

OneScreen for iPad is available on the App Store: [download OneScreen for iPad](https://apps.apple.com/us/app/onescreen-for-ipad/id6761702167) on the iPad you want to stream to. The Mac app's **Settings > About** also shows a QR code you can point the iPad's camera at to open the listing directly.

The iPad app carries the live viewer, a stream dashboard for switching between Macs and streams, framelines, display adjustments, and a draggable connection-quality HUD that shows how the link to the Mac is holding up.

To use the Capture One companion features, purchase and enable `Capture One Controls` inside OneScreen for iPad. This also unlocks the **Control Deck**, which turns the iPad into a control surface beside your primary monitor for rating, tagging, and reviewing captures.

Keep your Mac and iPad on the same local network, then start a stream from OneScreen for Mac and join it from OneScreen for iPad.

## Requirements

- macOS 14.0 or later
- OneScreen for iPad, on the same local network as the Mac
- **Screen Recording** permission granted to OneScreen
- **Local Network** access allowed for OneScreen
- Optional: **Accessibility** permission for Keep Cursor Off Display, full screen helpers, and window placement
- Optional: [NDI Tools](https://ndi.video/tools/) installed on the Mac, and only if you switch the streaming engine to NDI — the HEVC engine is built in and needs nothing installed
- Optional: Capture One, for companion controls and window targeting

## Installation

1. Download the [latest release](https://github.com/spotdgtl/OneScreen/releases/latest).
2. Move `OneScreen.app` to `/Applications`.
3. Launch it from `/Applications`, Launchpad, or Spotlight.
4. Complete the first-run setup inside the app.
5. Grant **Screen Recording** when prompted.
6. Allow **Local Network** access when macOS asks.
7. Install [NDI Tools](https://ndi.video/tools/) only if you intend to switch the streaming engine to NDI — skip it for HEVC.
8. Keep your Mac and iPad on the same network.

## First-Time Setup

On first launch, OneScreen walks you through the required checks before streaming starts:

- Screen Recording
- Accessibility
- NDI Tools (optional, and only for the NDI engine)
- Local Network

If any change still requires a relaunch, OneScreen will tell you in-app.

## Typical Workflow

1. Open OneScreen from the macOS menu bar.
2. Select a display, or choose a virtual iPad display preset and select your target window.
3. Leave the stream open (by default) or choose **Private Stream** by clicking the lock icon.
4. Click **Start**.
5. On the iPad, join the open stream or pair with the Mac via the private QR code or passcode.
6. Begin viewing the stream, purchase and enable **Capture One Controls** in the settings for enhanced control over the Capture One app.

## Settings Overview

- **General** — open at login and Dock icon visibility
- **Stream** — streaming engine (HEVC or NDI), stream name, quality presets or custom size, frame rate, data rate and bit depth, color space, auto-start and auto-switch behavior, and virtual iPad display scale, placement, orientation, and stray-window handling
- **Receivers** — name presets, iPad viewer controls, Power Save, battery and connection-quality readouts, receiver alerts
- **Integrations** — Capture One integration and supported companion actions
- **Preview** — floating preview window behavior and appearance
- **Intermission** — logo + text, title card, or solid color modes, secondary displays, and a local Test mode
- **Hotkeys** — keyboard shortcuts for live controls
- **Permissions** — Screen Recording, Accessibility, optional NDI runtime, and Capture One status
- **License** — trial status and license management
- **Updates / About / Help** — automatic and manual update checks, version info, support contact, and diagnostics

## Helpful Links

- [Latest release](https://github.com/spotdgtl/OneScreen/releases/latest)
- [User manual](docs/user-manual.md)
- [Privacy Policy](docs/privacy.md)
- Optional, NDI engine only: [NDI Tools download](https://ndi.video/tools/) and [setup guide](https://docs.ndi.video/all/using-ndi/ndi-tools/ndi-tools-launcher)
- [Send feedback](https://www.spotdgtl.com/apps/feedback)
