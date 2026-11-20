# Ponskaarten (standalone app)

Offline Dutch study app for Portuguese speakers, packaged as a Progressive Web App (PWA).

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole app (UI, lessons, cards, logic) |
| `sw.js` | Service worker: caches the app so it works offline |
| `manifest.webmanifest` | App name, icon and standalone display mode |
| `icon-*.png` | Home screen icons |

## Publish with GitHub Pages (free)
1. Create a new **public** repository on GitHub, e.g. `ponskaarten`.
2. Upload all files from this folder to the repository root (*Add file → Upload files*).
3. *Settings → Pages → Build and deployment*: Source **Deploy from a branch**, branch **main**, folder **/ (root)** → Save.
4. After 1–2 minutes the app is live at `https://<user>.github.io/ponskaarten/`.

GitHub Pages serves over HTTPS, which service workers require.

## Install on iPhone
1. Open the URL in **Safari** (not Chrome; only Safari can install web apps on iOS 16 and older).
2. *Share → Add to Home Screen → Add*.
3. Open the app once while online so every file is cached. After that it works offline.

## Updating
Replace `index.html` and `sw.js` in the repository. The cache name in `sw.js` changes with every build,
so the installed app picks up the new version the next time it opens online.

## Data
- Progress is stored on the device (`localStorage`, key `ponskaarten.v1`). Nothing is sent to any server.
- Deleting the app from the home screen deletes its progress.
- Use *Guardar cópia do progresso* (bottom of the deck list) to save a backup file, and *Repor uma cópia* to restore it.
