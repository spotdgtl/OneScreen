# OneScreen Privacy & Network Notes

OneScreen is built for local display streaming. This note explains what the Mac app needs access to and what can leave the Mac during normal use.

## Local Streaming

OneScreen captures the display you choose only while streaming or previewing. The live video stream is sent over your local network using NDI so receivers, such as OneScreen for iPad, can view it.

OneScreen does not upload your live video stream to Spot Digital servers.

## Open NDI And Private Stream

`Open NDI` publishes a discoverable NDI source on the local network. Compatible NDI receivers on the same network may be able to find the stream.

`Private Stream` requires pairing with a QR code or manual passphrase and uses a random NDI group for the session. Private Stream is designed to limit discovery and receiver access for OneScreen receivers, but it should still be used on networks you trust.

## Receiver Controls

When OneScreen for iPad connects, receiver state is exchanged locally with the Mac. This can include receiver name, battery status, charging state, brightness, display profile state, frame rate, connection status, and receiver-control commands.

## Licensing, Updates, And Feedback

License activation, validation, revalidation, and deactivation may contact Lemon Squeezy and, when configured, OneScreen's entitlement service. The license key, optional checkout email, app bundle ID, app version, and this Mac's license instance ID may be used for those requests.

Update checks may contact Sparkle update feeds and GitHub release endpoints. These requests can include normal web request metadata, such as IP address and user agent.

The `Send Feedback` button is user-triggered. It copies a diagnostic summary to the clipboard and opens the feedback page. The summary can include app version, macOS version, streaming state, selected display summary, receiver summary, permission status, NDI runtime status, license status, last error, and diagnostic log paths. Review the copied text before sending it.

## Analytics And Crash Reporting

Release builds may include Sentry crash reporting when configured by OneScreen. Crash reports are used to diagnose stability issues and can include stack traces, app version, macOS version, device/runtime metadata, and crash timing. They do not include screen video, screenshots, or OneScreen diagnostic log files. Crash reporting can be turned off in Settings.

The current OneScreen Mac app does not include automatic product analytics.

## Permissions

- `Screen Recording`: lets OneScreen capture the selected display for preview and streaming.
- `Local Network`: lets OneScreen publish and discover local receivers and NDI streams.
- `Apple Events`: lets OneScreen send Capture One commands when companion controls are enabled.
- `Accessibility`: optional; used for Cursor Lock and fullscreen/window-targeting helpers.
