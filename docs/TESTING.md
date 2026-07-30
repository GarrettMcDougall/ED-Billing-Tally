# Version 1.11 verification

## Completed static checks

- `manifest.webmanifest` parses as valid JSON.
- `sw.js` passes Node JavaScript syntax validation.
- Both inline scripts extracted from `index.html` pass Node JavaScript syntax validation.
- Application version is consistently set to `1.11.0` in the HTML and service worker.
- The ZIP archive contains the complete repository, including dotfiles, icons, screenshots, and documentation.

## Update-system code checks

- The app registers the service worker with `updateViaCache: "none"`.
- Update checks are attached to application load, foreground resume, and network reconnection.
- The build fingerprint includes `index.html`, `manifest.webmanifest`, and `sw.js`.
- Updated service workers use `skipWaiting()` and `clients.claim()`.
- Same-origin app requests use network-first fetching with cached offline fallback.
- Update reload is deferred while a modal is open, with a 30-second maximum delay.

## Deployment smoke test

After publishing to GitHub Pages, verify once on a phone or desktop browser:

1. Open the site online and reload once.
2. Confirm the installed app opens offline.
3. Make a harmless repository change to `index.html` and publish it.
4. Reopen or resume the installed app while online.
5. Confirm the update screen appears briefly and the app reloads without clearing local shift data.

A full service-worker lifecycle test could not be executed in the current build environment because browser navigation to local HTTP and file origins is administratively blocked.
