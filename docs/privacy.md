# OneScreen Privacy Policy

Last updated: October 26, 2026

OneScreen is built for local display streaming. This page explains what the Mac app needs access to and what can leave the Mac during normal use.

## Local Streaming

OneScreen captures the display you choose only while streaming or previewing. The live video stream is sent over your local network using the streaming engine you choose — the built-in HEVC engine by default, or NDI — so receivers, such as OneScreen for iPad, can view it.

OneScreen does not upload your live video stream to Spot Digital servers.

## Open Stream And Private Stream

`Open Stream` publishes a stream that is discoverable on the local network. Over NDI, compatible NDI receivers on the same network may be able to find it.

`Private Stream` requires pairing with a QR code or manual passcode. Over NDI it uses a random NDI group for the session; over HEVC it also encrypts the video between the Mac and any receiver that supports encryption. Private Stream is designed to limit discovery and receiver access for OneScreen receivers, but it should still be used on networks you trust.

## Receiver Controls

When OneScreen for iPad connects, receiver state is exchanged locally with the Mac. This can include receiver name, battery status, charging state, brightness, display profile state, frame rate, connection status, receiver-control commands, and, while an iPad browses, the Capture One folder it has open.

## Capture One Browser

When the Capture One Browser switch is on in `Settings > Tools` and Capture One Studio shares a session with Live for Studio, OneScreen finds that share on your local network and tells connected iPads where it is. The iPads load pictures, star ratings and color tags from Capture One directly over the local network. When an iPad asks, OneScreen has Capture One read a folder, or a picture's shutter speed, aperture, ISO and focal length, and sends the answer to that iPad. None of this goes to Spot Digital servers.

## Shot List And Moodboard

A PDF shot list or moodboard you choose is copied into OneScreen's folder on this Mac (`~/Library/Application Support/OneScreen/ShotList`) and sent to connected iPads over the local network. The marks iPads make on it are kept with it. Choosing another document replaces the copy, and removing a document deletes it.

## Licensing, Updates, And Feedback

License activation, validation, revalidation, and deactivation may contact Lemon Squeezy and, when configured, OneScreen's entitlement service. The license key, optional checkout email, app bundle ID, app version, and this Mac's license instance ID may be used for those requests.

Update checks may contact OneScreen's update feed and GitHub release endpoints. These requests can include normal web request metadata, such as IP address and user agent.

The `Contact Support` button in `Settings > Help` is user-triggered. It copies a redacted diagnostic summary to the clipboard and opens the feedback page. The summary can include app version, macOS version, streaming and paused state, connected receiver app versions, permission status, NDI runtime status, license and trial status, last error, and diagnostic log paths. Display names, receiver names, your home folder path, email addresses, and license keys are redacted before the summary is copied. Review the copied text before sending it.

## Connection Log On This Mac

OneScreen keeps a small connection log on this Mac, so a connection problem can be looked at after it has happened. It is kept whether or not `Detailed Diagnostic Logging` is on.

The log records when a stream starts, stops, and is paused; when Capture One stops or starts answering, with this Mac's one-minute load average; each receiver's connection reading; when a receiver's video connection stalls, is rebuilt, or recovers; the stream's data rate and the reason for each change to it; counts for each minute, such as frames sent, their sizes, and how long they took to send; and the names, kinds, and state of this Mac's network interfaces, such as `en0`, Wi-Fi or Ethernet, and whether each is up.

The log does not record network names, network addresses, or anything from the picture. A receiver appears as a short ID. Its name is added only while `Detailed Diagnostic Logging` is on.

The log is stored in `~/Library/Logs/OneScreen`. It is limited to 4 MB, plus one older file of the same size, and the oldest entries are deleted as it fills. It leaves this Mac only inside the zip that `Diagnostic Logs` in `Settings > Help` exports, and only if you send that zip to someone. Receiver names are redacted in the zip.

## Analytics And Crash Reporting

Release builds may include crash reporting when configured by OneScreen. Crash reports are handled for OneScreen by a third-party crash reporting service. They are used to diagnose stability issues and can include stack traces, app version, macOS version, device/runtime metadata, and crash timing. They do not include screen video, screenshots, or OneScreen diagnostic log files. Crash reporting can be turned off in Settings.

The current OneScreen Mac app does not include automatic product analytics.

## Permissions

- `Screen Recording`: lets OneScreen capture the selected display for preview and streaming.
- `Local Network`: lets OneScreen publish and discover local receivers and streams over either engine.
- `Apple Events`: lets OneScreen send Capture One commands when companion controls are enabled, and read folders and a picture's exposure for Capture One Browser.
- `Accessibility`: optional; used for Keep Cursor Off Display and full screen/window-targeting helpers.
