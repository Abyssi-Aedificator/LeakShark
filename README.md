# LeakShark

Track subscriptions, normalize billing cycles, and see what you actually spend each month.

A minimal, single-file PWA with a bento-grid dashboard. No build step, no dependencies — open it, add subscriptions, done.

## Features

- **Bento dashboard** — monthly total, plus active/inactive subscription counts and billing-cycle breakdowns
- **Cycle normalization** — weekly and yearly plans are converted to a true monthly cost
- **Add / edit / delete** subscriptions with name, cost, billing cycle, next renewal, and optional cancel date
- **Active / Inactive tracking** — a subscription moves to Inactive automatically once its cancel date passes
- **Collapsible form panel** — the add/edit form tucks away until you need it
- **localStorage persistence** — your data stays on your device, no accounts or servers
- **Installable PWA** — manifest + service worker with offline caching and app icons

## Quick start

Serve the folder and open `index.html`:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080`. Serving over HTTP(S) enables the service worker, offline support, and the install prompt. Opening `index.html` directly from disk (`file://`) still works, but PWA features are skipped.

## Tech stack

- Plain HTML + CSS (inline) + vanilla JS
- `localStorage` for persistence
- `manifest.webmanifest` + `sw.js` for PWA/offline
- Icons: `icon.svg` (source) with generated PNGs (`icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png`)

## Project structure

```
index.html              App (markup, styles, logic)
manifest.webmanifest    PWA manifest
sw.js                   Service worker / offline cache
icon.svg                Icon source (SVG)
*.png                   Generated icon sizes
changelog.txt           Version history
```

## License

MIT
