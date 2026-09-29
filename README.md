# Emino World — Website

Static bilingual (EN / 繁中) website built from plain HTML and JavaScript.

## Structure
- `index.html` — homepage; keep it synchronized with `Home.dc.html`
- `Home / Services / About / Team / Contact` `.dc.html` — main pages
- `Service - *.dc.html` — the six service detail pages
- `Terms and Conditions.dc.html`, `Privacy Policy.dc.html` — legal pages
- `SiteFooter.dc.html` — shared footer, embedded by every page
- `support.js` — runtime for the `.dc.html` components (required)
- `image-slot.js` + `.image-slots.state.json` — team portrait handling
- `assets/` — logo, portraits, background images, including the Management & Market-Entry hero image

## Deploy to Cloudflare Pages
The generated site is static and has no framework build step.

**Option A — Dashboard (drag & drop)**
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → Upload assets.
2. Drag the contents of this folder (not the folder itself) so `index.html` sits at the root.
3. Deploy.

**Option B — Wrangler CLI**
```bash
npx wrangler pages deploy . --project-name eminoworld --branch main
```
Run from inside this folder.

- **Build command:** none
- **Build output directory:** `/` (the folder root)

## Notes
- Keep `index.html` and `Home.dc.html` synchronized, and update page metadata and `sitemap.xml` when adding or renaming pages.
- Fonts load from Google Fonts over the network.
- Page files use the `.dc.html` extension and link to each other by that exact name — keep the filenames as-is.
- Team portraits are baked into `assets/` and referenced directly, so they appear instantly. The drag-to-replace feature only works inside the design editor, not on the live site.
