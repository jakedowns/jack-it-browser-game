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
- `Q` / `E` — tap once to lower / raise forks; the mast travels on its own
- `P` — unplug / plug charger cord
- `G` — debug menu (switch to camera-oriented controls, pin FPV, teleports, battery/cargo reset)
- `T` — run the 8-test physics regression suite
- `R` — restart the current bay
- Mouse drag — virtual stick; wheel or two-finger pinch — zoom

## GitHub Pages

Pages deploys directly from **`main` / `(root)`**. The repo root contains `index.html` and `.nojekyll`, so no `gh-pages` branch or copy step is needed.

The `origin` remote is already configured for this checkout. From the Mac hosting this shared folder:

```bash
cd /path/to/jack-it
git remote -v
git push -u origin main
```

Then in the GitHub repository: **Settings → Pages → Build and deployment → Deploy from a branch**, choose **`main`** and **`/ (root)`**.

After the site is confirmed live on `main`, the obsolete deployment branch can be removed:

```bash
git push origin --delete gh-pages
```

Live simulator: [https://jakedowns.github.io/jack-it-browser-game/](https://jakedowns.github.io/jack-it-browser-game/)

The page loads Three.js and the `box3d-wasm` package from jsDelivr, so the browser needs network access.
