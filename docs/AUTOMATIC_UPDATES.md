# Automatic update system

Version 1.11 adds two complementary update paths.

## Service-worker update

The application registers `sw.js` with `updateViaCache: "none"` and calls `registration.update()` whenever the app launches, resumes, or reconnects. A changed service worker installs its fresh app shell, calls `skipWaiting()`, claims open clients, and triggers a controlled reload.

## Build-fingerprint update

The open page also fetches fresh copies of:

- `index.html`
- `manifest.webmanifest`
- `sw.js`

It creates a SHA-256 fingerprint and compares it with the previous online check. This detects an updated app page even when the service-worker script itself was not changed.

## Reload safety

When an update is ready, the app shows an updating screen. It waits for an open modal to close before reloading, up to a maximum of 30 seconds. LocalStorage is not cleared.

## Limitations

Installed web apps cannot be forcibly updated while fully closed. An online launch or resume is required. Changes limited to documentation or other files outside the three-file fingerprint do not trigger an application reload.
