# PWA deployment, installation, and automatic updates

## GitHub Pages

1. Upload all files and folders in this package to the repository root.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Select `main` and `/ (root)`.
5. Save and wait for the GitHub Pages deployment to finish.

Every commit to the selected branch is then published automatically by GitHub Pages.

## Install on iPhone or iPad

1. Open the GitHub Pages URL in Safari.
2. Tap **Share**.
3. Select **Add to Home Screen**.
4. Tap **Add**.

## Install on Android

1. Open the site in Chrome.
2. Open the browser menu.
3. Select **Install app** or **Add to Home screen**.

## Install on desktop

In Chrome or Edge, use the install icon in the address bar or the browser menu.

## Offline use

The first load must be online. The service worker caches the app shell so the calculator can reopen offline. LocalStorage data remains tied to the specific browser/device.

## Automatic update behaviour

The app checks GitHub Pages when it:

- launches while online;
- returns to the foreground;
- reconnects to the internet.

It checks `index.html`, `manifest.webmanifest`, and `sw.js`. When any of these files changes, the new build is downloaded and the app reloads after any open modal is closed. A 30-second safety limit prevents an old build from remaining open indefinitely.

The update does **not** erase LocalStorage. Active shifts, completed shifts, pinned codes, settings, and theme selection remain on the device.

A phone cannot be forced to update while the app is fully closed. The update occurs the next time the app launches or resumes with an internet connection.

## Publishing a new release

For a clean release:

1. Replace the changed repository files.
2. Update the visible version and `VERSION` in `index.html`.
3. Update `APP_VERSION` in `sw.js`.
4. Commit and push to `main`.
5. Wait for GitHub Pages to finish deploying.

The current application and service-worker version is **1.11.0**.

## Sitemap

Update the placeholder URL in `sitemap.xml` to your final GitHub Pages address.
