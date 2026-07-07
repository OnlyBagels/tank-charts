# Tank Chart — installable PWA

A stick-to-gallon calibration chart for horizontal cylindrical tanks. Works
offline once installed and runs full-screen on iPad/iPhone.

## Files
- `index.html` — the stick-to-gallon chart + OPV percent-full (self-contained: HTML, CSS, JS)
- `manifest.webmanifest` — PWA metadata (name, icons, standalone display)
- `sw.js` — service worker (offline cache of the app shell)
- `icons/` — app icons (192, 512, 512-maskable, and a 180px Apple touch icon)
- `.nojekyll` — tells GitHub Pages to serve files as-is

All asset paths are **relative**, so it works from a GitHub Pages project
subpath (`https://<user>.github.io/<repo>/`).

## Deploy to GitHub Pages

```bash
cd tank-chart-pwa
git init
git add .
git commit -m "Tank Chart PWA"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo>.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: Deploy from
a branch → Branch: `main` / root → Save.** After a minute the site is live at
`https://<your-username>.github.io/<repo>/`.

## Install on iPad
1. Open the Pages URL in **Safari** (must be Safari, not Chrome).
2. Tap the **Share** button → **Add to Home Screen** → **Add**.
3. Launch it from the home screen — it opens full-screen and works offline.

## Updating the app
Edit the files, bump `CACHE` in `sw.js` (e.g. `tank-chart-v2`), commit, and
push. The new service worker replaces the old cache on next launch.
