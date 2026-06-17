# OneScreen for Mac

<p align="center">
  <img src="docs/images/onescreen-logo.png" alt="OneScreen icon" width="96" />
</p>

<p align="center">
  <a href="https://github.com/spotdgtl/OneScreen/releases/latest"><img src="https://img.shields.io/badge/Download-latest%20release-black?style=for-the-badge&logo=github" alt="Download latest release" height="24" /></a>
  <a href="https://github.com/spotdgtl/OneScreen/releases/latest"><img src="https://img.shields.io/badge/macOS-14.0%2B-1793d1?style=for-the-badge&logo=apple&logoColor=white&labelColor=555555" alt="macOS 14.0 or later" height="24" /></a>
  <a href="https://testflight.apple.com/join/ywJPBZS2"><img src="https://img.shields.io/badge/iPad-TestFlight%20beta-0a84ff?style=for-the-badge&logo=appstore&logoColor=white&labelColor=555555" alt="iPad TestFlight beta" height="24" /></a>
  <img src="https://img.shields.io/badge/Swift-5-F05138?style=for-the-badge&logo=swift&logoColor=white&labelColor=555555" alt="Swift 5" height="24" />
  <a href="docs/distribution.md"><img src="https://img.shields.io/badge/Apple%20Notarized-%E2%9C%93-4cbb17?style=for-the-badge&logo=apple&logoColor=white&labelColor=555555" alt="Apple notarized" height="24" /></a>
  <a href="docs/distribution.md"><img src="https://img.shields.io/badge/Sparkle-updates-4cbb17?style=for-the-badge&labelColor=555555" alt="Sparkle updates enabled" height="24" /></a>
  <a href="docs/privacy.md"><img src="https://img.shields.io/badge/Sentry-crash%20reporting-362d59?style=for-the-badge&logo=sentry&logoColor=white&labelColor=555555" alt="Sentry crash reporting" height="24" /></a>
</p>

OneScreen is a Mac app that wirelessly streams an existing display or virtual iPad-sized display to the **OneScreen for iPad** companion app over your local network, turning any iPad into a dedicated viewing monitor. It uses the NDI protocol for low-latency video and adds private pairing, live display controls, and optional Capture One integration.

## Highlights

- **Create a virtual, iPad-sized display on demand** so you can stream a dedicated workspace instead of mirroring an existing screen.
- **Stream an existing Mac display when needed** for manual capture setups or advanced workflows.
- **Public or Private stream modes**, with QR code or manual passphrase pairing to keep your stream off other receivers on the network.
- **Inline stream controls** to pause, resume, trigger an intermission screen, lock the receiver, or rotate the display.
- **Floating Preview window** that mirrors what the iPad is currently showing, so you don't have to look at the receiver to check the output.
- **Manage connected iPads from the Mac**, including custom names and color labels, brightness, display profile selection, framelines control, discovery toggle, return-to-live stream toggle, per-receiver pause, and per-receiver lock.
- **Power Save** dims all of the connected receivers to extend iPad battery life during down time with the press of a button, and restores them on demand.
- **Bandwidth presets, plus custom FPS, quality, and color space** easy preset modes and custom tuning options to tweak the stream depending on your network.
- **Automatic display fallback** keeps the stream alive if the source display disconnects — or you can have it terminate cleanly instead.
- **Global hotkeys** for pause/resume, intermission, preview window, fullscreen, lock/unlock, and Power Save.
- **Capture One Controls integration** iPad companion actions like navigation, ratings, color tags, camera controls, capture button, Live View, overlays, grid, clear compare, and image rotation toggles.

## Trial and Licensing

OneScreen includes a 3-day free trial with full streaming on each Mac. You can [purchase an early license](https://spotdgtl.lemonsqueezy.com/checkout/buy/d192eedf-4770-4e21-bb20-bfbb37f82aeb?discount=0) to keep using the Mac app during the beta and support development before the iPad app reaches the App Store.

If you want to test longer before purchasing, email [graham@spotdgtl.com](mailto:graham@spotdgtl.com) for a beta license. License activation, validation, revalidation, and removal are all handled in **Settings > License**.

## OneScreen for iPad Beta

OneScreen for iPad is currently available as a beta through TestFlight. The official iPad app has not launched on the App Store yet. Open the [public TestFlight link](https://testflight.apple.com/join/ywJPBZS2) on your iPad, install Apple's TestFlight app if prompted, then install OneScreen from TestFlight.

To try the Capture One companion features during the beta, enable `Capture One Controls` inside OneScreen for iPad. The beta uses Apple's sandbox purchase environment, so you may see a purchase confirmation, but no real payment is processed and you will not be charged.

Keep your Mac and iPad on the same local network, then start a stream from OneScreen for Mac and join it from OneScreen for iPad.

## Requirements

- macOS 14.0 or later
- OneScreen for iPad, on the same local network as the Mac
- [NDI Tools](https://ndi.video/tools/) installed on the Mac (provides the NDI runtime)
- **Screen Recording** permission granted to OneScreen
- Optional: **Accessibility** permission for Keep Cursor Off Stream and fullscreen window helpers
- Optional: Capture One, for companion controls and window targeting

## Installation

1. Download the [latest release](https://github.com/spotdgtl/OneScreen/releases/latest).
2. Move `OneScreen.app` to `/Applications`.
3. Launch it from `/Applications`, Launchpad, or Spotlight.
4. Complete the first-run setup inside the app.
5. Grant **Screen Recording** when prompted.
6. Install [NDI Tools](https://ndi.video/tools/) if the NDI runtime isn't already present.
7. Allow **Local Network** access when macOS asks.
8. Keep your Mac and iPad on the same network.

## First-Time Setup

On first launch, OneScreen walks you through the required checks before streaming starts:

- Screen Recording
- NDI Tools
- Local Network
- Accessibility (optional)

If any change still requires a relaunch, OneScreen will tell you in-app.

## Typical Workflow

1. Open OneScreen from the macOS menu bar.
2. Select a display, or choose a virtual iPad display preset.
3. Leave stream open or choose **Private Stream** by clicking the lock icon.
4. Click **Start**.
5. Join the public stream or choose **Join Private Stream** to pair with the Mac via a private QR code or passphrase.
6. Begin viewering the stream or enable **Capture One Controls** in settings for enhanced control over the image.

## Settings Overview

- **Stream** — stream name, bandwidth mode, output color space, Keep Cursor Off Stream, display visibility, automatic display fallback
- **Receivers** — name presets, Power Save, receiver alerts
- **Stream Tools** — Capture One integration and supported companion actions
- **Preview** — floating preview window behavior
- **Intermission** — logo + text, title card, or solid color modes
- **Hotkeys** — keyboard shortcuts for live controls
- **Permissions** — Screen Recording, NDI, Accessibility, and Capture One status
- **License** — trial status and license management

## Helpful Links

- [Latest release](https://github.com/spotdgtl/OneScreen/releases/latest)
- [User manual](docs/user-manual.md)
- [Privacy Policy](docs/privacy.md)
- [NDI Tools download](https://ndi.video/tools/)
- [NDI Tools setup guide](https://docs.ndi.video/all/using-ndi/ndi-tools/ndi-tools-launcher)
- [Send feedback](https://www.spotdgtl.com/apps/feedback)
