# Ontario ED Billing Calculator

A device-local, installable Ontario Emergency Department billing calculator built from the curated Ontario Schedule of Benefits reference used by the project.

## Features

- Anonymous case-based shift logging
- Automatic Ontario ED assessment time-band selection
- Standard **Reassessment** button using the selected log-time band
- **Next time-block reassessment** for crossing day/evening/night/weekend bands
- Procedural sedation calculator with anaesthesia units and modifiers
- Automatic eligible ED time premiums for procedure/resuscitation cases
- Custom pinned codes and usage-based recommendations
- Hold a quick code to pin or unpin it
- Persistent **Undo last code** control
- Swipe-left deletion in the ledger
- Shift totals, workload-premium estimates, CSV export, and JSON backup
- Three selectable visual themes
- Progressive Web App installation, offline app-shell caching, and automatic GitHub update checks

## Privacy

The app has no backend, analytics, advertising, or telemetry. Shift data is stored in browser LocalStorage on the device. **Do not enter patient identifiers.**

## Run locally

Open `index.html` in a browser. Some PWA features, particularly service workers, require HTTPS or localhost.

## Deploy with GitHub Pages

1. Place the repository files at the repository root.
2. Open **Settings → Pages**.
3. Choose **Deploy from a branch**.
4. Select `main` and `/ (root)`.
5. Save and use the generated Pages URL.

See [`PWA_DEPLOYMENT.md`](PWA_DEPLOYMENT.md) for installation and automatic-update instructions.

## Disclaimer

This application provides estimates and workflow support only. It does not replace the current Ontario Schedule of Benefits, Ministry of Health rules, local billing policies, or formal claims adjudication. Users remain responsible for claim accuracy and eligibility.
