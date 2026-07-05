# Prachi Randeria — Portfolio

Personal portfolio site for Prachi Randeria (Software Engineer, cloud/backend/platform).

**Live:** https://omkartralsawala.github.io/prachi-portfolio/

## Stack

Single-page static site built with the **dc-runtime** (Claude Design). No build
step — `index.html` is the page template, `support.js` is the runtime that
mounts it. Three.js (particle background) and Google Fonts load from CDNs at
runtime; nothing is bundled.

Current design: **Amethyst Glass** (glassmorphic dark theme), imported from the
Claude Design project.

## Files

| Path | Purpose |
|------|---------|
| `index.html` | The page — dc template + inline `data-dc-script` logic |
| `support.js` | Generated dc-runtime. **Do not hand-edit** — regenerated from source |
| `uploads/prachi-resume.pdf` | Résumé linked from the site |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll) |

## Run locally

```bash
python3 -m http.server 8080
# open http://localhost:8080/
```

Must be served over HTTP (not opened as a `file://`) so `support.js` and the
CDN assets load.

## Deploy

GitHub Pages, source = `main` branch / root. Push to `main` and Pages rebuilds
automatically:

```bash
git add index.html && git commit -m "…" && git push origin main
```

## Update the design

The page is authored in the Claude Design project. To pull a new revision,
re-import the `.dc.html` file, overwrite `index.html`, and push. `support.js`
only needs replacing if the dc-runtime version changes.
