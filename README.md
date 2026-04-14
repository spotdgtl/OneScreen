# OneScreen for macOS

<p align="center">
  <img src="docs/images/onescreen-logo.png" alt="OneScreen icon" width="96" />
</p>

OneScreen is a macOS menu bar app that streams a display from your Mac to OneScreen for iPad over your local network. It also adds private pairing, live display profile controls, and Capture One Remote Controls through the companion iPad app.

[![Download for macOS](https://img.shields.io/badge/Download-latest%20release-black?style=for-the-badge&logo=github)](https://github.com/spotdgtl/OneScreen/releases/latest)
[![Latest version](https://img.shields.io/github/v/release/spotdgtl/OneScreen?display_name=release&style=for-the-badge)](https://github.com/spotdgtl/OneScreen/releases/latest)
[![Platform](https://img.shields.io/badge/macOS-14.0%2B-blue?style=for-the-badge&logo=apple)](https://github.com/spotdgtl/OneScreen/releases/latest)

Download the latest version from [GitHub Releases](https://github.com/spotdgtl/OneScreen/releases/latest).

## Highlights

- Stream any Mac display to OneScreen for iPad over your local network.
- Create a virtual iPad-sized display on demand instead of having to mirror an existing display.
- Choose between `Public` or `Private` stream modes with QR code or manual passphrase pairing.
- Use inline controls to pause, resume, set an intermission, lock, or rotate your display.
- Open a floating Preview Window to see your virtual display without having to look at the receiver. 
- Manage connected receivers from the Mac with naming presets, color labels, brightness control, display profiles, ping, and more.
- Toggle `Power Save` to dim connected receivers or restore them later to save battery life on host receivers.
- Configure stream bandwidth presets or custom FPS and quality, plus output color space selection.
- Enable automatic display fallback if the selected display disappears while streaming or set the stream to terminate.
- Assign hotkeys for pause/resume, intermission, preview window, fullscreen, lock/unlock controls, and power save features.
- Add optional Capture One integration for actions like navigation, ratings, color tags, camera controls, capture, Live View, overlay, grid, clear compare, and image rotation.

## Trial And Licensing

OneScreen includes a 3-day free trial with full streaming access on each Mac. License activation, validation, revalidation, and removal are handled inside the app in `Settings > License`.

## Requirements

- macOS 14.0 or later
- OneScreen for iPad on the same local network
- `NDI Tools` installed on the Mac
- `Screen Recording` permission enabled for OneScreen
- Optional: `Accessibility` if you want Cursor Lock or fullscreen window helpers
- Optional: Capture One if you want companion controls and window targeting

## Installation

1. Download the [latest release](https://github.com/spotdgtl/OneScreen/releases/latest).
2. Move `OneScreen.app` to `/Applications`.
3. Launch OneScreen from `/Applications`, Launchpad, or Spotlight.
4. Complete the first-run setup inside the app.
5. Grant `Screen Recording` when prompted.
6. Install [NDI Tools](https://ndi.video/tools/) if the NDI runtime is not already present.
7. Allow `Local Network` access when macOS asks.
8. Keep your Mac and iPad on the same network.

## First-Time Setup

On first launch, OneScreen walks through the required checks before streaming starts:

- `Screen Recording`
- `NDI Tools`
- `Local Network`
- Optional `Accessibility`

If a setup change still needs a relaunch, OneScreen will tell you inside the app.

## Typical Workflow

1. Open OneScreen from the macOS menu bar.
2. Select a display or choose a virtual iPad display preset.
3. Pick `Open NDI` or `Private Stream`.
4. Click `Start`.
5. Join the stream from OneScreen for iPad.
6. Use preview, intermission, fullscreen, receiver, or Capture One controls as needed.

## Settings Overview

OneScreen includes dedicated settings for:

- `Stream`: source name, bandwidth mode, output color space, Cursor Lock, and automatic display fallback
- `Receivers`: receiver name presets, power save, and receiver alerts
- `Integrations`: Capture One integration and supported companion actions
- `Preview`: floating preview window behavior
- `Intermission`: logo plus text, title card, or solid color intermission modes
- `Hotkeys`: keyboard shortcuts for live controls
- `Permissions`: Screen Recording, NDI, Accessibility, and Capture One permission status
- `License`: trial status and license management

## Helpful Links

- [Latest release](https://github.com/spotdgtl/OneScreen/releases/latest)
- [User manual](docs/user-manual.md)
- [NDI Tools download](https://ndi.video/tools/)
- [NDI Tools setup guide](https://docs.ndi.video/all/using-ndi/ndi-tools/ndi-tools-launcher)
- [Send feedback](https://www.spotdgtl.com/apps/feedback)
