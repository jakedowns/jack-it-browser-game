# PALLET // RUNNER

Single-file 3D warehouse simulator: Three.js + Box3D (WASM) physics, an articulated electric walkie pallet jack, 27 loose rigid-body cartons, FPV fork-alignment PiP, charger cord/battery management, three delivery bays, and an in-page physics regression suite.

## Run locally

No build step. Serve the folder over HTTP so the ES modules and WASM can load:

```bash
cd jack-it
python3 -m http.server 8000
```

Open <http://localhost:8000/>.

## Controls

- `W` / `S` — throttle / reverse (truck-local)
- `A` / `D` — steer
- `Q` / `E` — lower / raise forks
- `P` — unplug / plug charger cord
- `G` — debug menu (switch to camera-oriented controls, pin FPV, teleports, battery/cargo reset)
- `T` — run the 8-test physics regression suite
- `R` — restart the current bay
- Mouse drag — virtual stick; wheel — zoom

## GitHub Pages

This repository contains a `gh-pages` branch with `index.html` and `.nojekyll` at the branch root. GitHub Pages can serve it directly.

From the Mac hosting this shared folder:

The `origin` remote is already configured for this checkout. From the Mac hosting this shared folder:

```bash
cd /path/to/jack-it
git remote -v
git push -u origin main
git push origin gh-pages
```

If you need to recreate the remote elsewhere:

```bash
git remote add origin https://github.com/jakedowns/jack-it-browser-game.git
```

Then in the GitHub repository: **Settings → Pages → Build and deployment → Deploy from a branch**, choose **`gh-pages`** and **`/ (root)`**.

Public URL:

```text
https://jakedowns.github.io/jack-it-browser-game/
```

The page loads Three.js and the `box3d-wasm` package from jsDelivr, so the browser needs network access.
