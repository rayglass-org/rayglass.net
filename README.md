# RayGlass website (rayglass.net)

Static landing page + download instructions. No build step, no framework — just
HTML/CSS. Served from the **public** repo `rayglass-org/rayglass.net` via GitHub
Pages. This folder is the source of truth; copy it to the public repo root.

## Files

- `index.html` — landing page (hero, NOT-FOR-CLINICAL banner, downloads, features, footer).
- `license.html` — full EULA (`/license`).
- `styles.css` — single stylesheet.
- `robots.txt` + `<meta robots noindex>` — site is **not indexed** (pre-launch).
- `CNAME` — custom domain `rayglass.net`.
- `.nojekyll` — serve files as-is (no Jekyll).
- `assets/` — screenshots / video (see backlog below).

## Deploy (one-time)

1. Copy `docs/website/*` (including dotfiles: `.nojekyll`, `CNAME`) into the root
   of `rayglass-org/rayglass.net`.
2. Repo Settings > Pages: Source = `Deploy from a branch`, branch `main` / `/root`.
3. Set custom domain `rayglass.net`, enable **Enforce HTTPS**.
4. DNS: `CNAME rayglass.net -> rayglass-org.github.io` (or apex A/AAAA records for
   a bare domain — see GitHub Pages docs).

Download buttons already point at
`https://github.com/rayglass-org/rayglass.net/releases/latest/download/<asset>`,
which the release workflow (`.github/workflows/release.yml`) populates with:

| Asset | OS |
|---|---|
| `RayGlass-macos-arm64.zip` | macOS (Apple Silicon), portable .app |
| `RayGlass-macos-arm64.dmg` | macOS disk image |
| `RayGlass-windows-x64-portable.zip` | Windows x64 portable |
| `*.whl` | `pip install rayglass` |

## Media backlog (add later)

Drop files into `assets/` — the `<img>`/`<video>` slots in `index.html` already
point at these paths, so no layout changes are needed:

- [ ] `assets/hero.png` — main viewer screenshot (hero).
- [ ] `assets/walkthrough.mp4` + `assets/walkthrough-poster.png` — 30-60s GUI demo.
- [ ] `assets/features/mpr.png` — MPR / 3-plane.
- [ ] `assets/features/vr.png` — volume rendering.
- [ ] `assets/features/import.png` — study import / database.
- [ ] `assets/features/plugins.png` — segmentation / measurements.
- [ ] `assets/cli.svg` — optional termshot/asciinema of a `rayglass` command.

Guidance: PNG/WebP stills, MP4 (H.264) video with a poster, keep each asset
< ~3 MB for fast Pages load. **No PHI** — use the anonymized corpus only.
