# VakilStay — Stay & Explore Shiraz

A responsive, visitor-friendly static travel and accommodation guide for Shiraz, Iran. Built for GitHub Pages at **https://bita-prsp.github.io/Vakilstay/**.

## Included
- Existing visual identity: the header, loader, PWA icons, and app metadata use `images/Logo/logo.png` from the repository. Keep the existing `images/Logo/logo.png` file when replacing files.
- Weather forecast for Shiraz (current conditions and up to seven days) powered by the free Open-Meteo forecast API. A fallback state appears if the API/network is unavailable.
- Installable PWA setup (`manifest.webmanifest`, `sw.js`, Apple touch icon metadata); the browser decides when installation is available. On iPhone, use Safari → Share → Add to Home Screen.
- Loading screen inspired by ancient Persian/Mesopotamian motifs, with a restrained cuneiform-inspired decorative line.
- Share links use the canonical GitHub Pages address and Open Graph/Twitter metadata for link previews.
- Existing accommodation, place cards, filters, saved items, trip planning, maps and gallery retained.
- Small footer analytics strip for 30-day page views and lifetime totals, with no fake placeholder counts.

## Deploy to GitHub Pages
1. Download and extract the ZIP.
2. Upload/replace `index.html`, `style.css`, `script.js`, `README.md`, `manifest.webmanifest`, `sw.js`, and the included `assets/` directory in the root of `Bita-prsp/Vakilstay`.
3. **Keep** the repository's existing `images/Logo/logo.png`, `guide.pdf`, and any real accommodation photos that are not included in this bundle. The original logo path is intentionally referenced as `images/Logo/logo.png`.
4. In repository Settings → Pages, make sure the intended branch/root is published.
5. Wait for the deployment and hard-refresh the site. PWA install prompts require HTTPS and browser support.

## GitHub Page Insights configuration
The UI requests the platform ID `vakilstay` from the existing GitHub Page Insights Worker. The ID must exist in that service and the worker must allow public read access/CORS from `https://bita-prsp.github.io`. If this fork has not yet been registered in the Insights dashboard/API, register `vakilstay` there first. The frontend cannot create a platform or infer lifetime totals if the API does not expose them. When unavailable, the UI shows a dash rather than invented statistics.

## Notes
- Weather is provided by Open-Meteo; forecasts are estimates and can change.
- The English toggle translates key navigation and common controls, but the original Persian editorial copy is retained in places. A complete professionally edited English version can be added as a separate translation pass.
- The accommodation links and contact details remain the existing project values; verify availability and contact details before publishing.
- Static GitHub Pages cannot send notifications or store user plans across devices. Saved preferences remain in the visitor's browser.
