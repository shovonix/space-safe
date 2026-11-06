# Space Safe

Drop in a thumbnail, see YouTube-style overlays before uploading. Live at https://safe.shovonix.dev

## How this repo works
- Everything is in `index.html`. No build step, no framework, no npm. Keep it that way unless Shovon asks.
- Images are read in the browser and never uploaded. Keep it that way.
- Preview locally: `python3 -m http.server 8000`, then open http://localhost:8000
- `landing/space-safe/` is the landing page.

## YouTube layout
- Overlays copy YouTube's layout as of late 2026 (home feed dark/light, phone, sidebar "up next", link-preview crops, timestamp badge).
- When YouTube changes its layout, update sizes and positions in one place and note the date in the README.
- It's a guide, not a pixel-perfect copy. Don't use YouTube logos or claim affiliation.

## Space key (signature of every Space app)
- Uses the shared `SpaceKey` helper and the on-screen keycap (`#spacehint`). It never fires while typing in a field.
- Keep the Space key working and fun after every change.

## Design
- Black and white only. Tokens: `--bg #070707`, `--fg #F0F0EE`, `--hair #2A2A2C`. Red only for warnings.
- Fonts: Archivo (UI), JetBrains Mono (numbers, keycap).

## Rules
- After changing any cached file, bump `CACHE` in `sw.js` so installed copies update.
- No analytics or tracking scripts.
- Licence: all rights reserved, no open-source licence. Don't add one.
- Ask before adding a dependency, a build step, or a backend.

## Workflow
- Work on the Mac in `~/Sites/space/space-safe`. Preview locally, commit small, push to `main`.
- Live files: `/home/safe/htdocs/safe.shovonix.dev` (CloudPanel site user `safe`). Landing page (`landing/space-safe/`) lives on the hub at `/home/shovonix/htdocs/shovonix.dev/space-safe/`; deploy it with `deploy-space hub`.
- Deploy: push to `main`, then on the VPS run `deploy-space safe` as root. It pulls `main` as user `safe` (fast-forward only) and checks the site returns 200.
- Git data lives outside the web root at `/home/safe/space-safe.git` (so `.git` is never served). `landing/`, `README.md` and `CLAUDE.md` are excluded from the live folder via sparse-checkout.
- Never edit the live files on the VPS directly.
