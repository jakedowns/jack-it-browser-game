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

```bash
cd /path/to/jack-it
git remote add origin git@github.com:YOUR_USER/YOUR_REPO.git
git push -u origin main
git push origin gh-pages
```

Then in the GitHub repository: **Settings → Pages → Build and deployment → Deploy from a branch**, choose **`gh-pages`** and **`/ (root)`**.

Public URL:

```text
https://YOUR_USER.github.io/YOUR_REPO/
```

The page loads Three.js and the `box3d-wasm` package from jsDelivr, so the browser needs network access.
