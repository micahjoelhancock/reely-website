# Reely website

Static site built from `reely-figma-motion-v3.2.html`. The original was one 16.5 MB file with every
font, image and video embedded inline. Here those are split into `assets/` so the page itself is
~150 KB and media loads only when it is needed, and can be cached.

- `index.html`: the page (markup, styles, motion scripts)
- `assets/fonts`, `assets/img`, `assets/video`: content-hashed files, safe to cache forever
- `_headers`: cache rules for Netlify / Cloudflare Pages

No build step. Serve it from any static host (Netlify, Vercel, Cloudflare Pages, GitHub Pages),
or locally with `python3 -m http.server` in this folder. Open it over http, not as a `file://`,
so the WebGL screens can read the video textures.

Motion turns off for visitors with "reduce motion" set.

The layout follows the Figma file "Reely Website — Design Baseline" (frame "Desktop v2"). Headings and body
copy ask for Neue Haas Grotesk first and fall back to Helvetica / Arial until a web licence is loaded.
The "Subscribe for Snippets" form in the contact section is built but hidden until it has somewhere to send sign-ups.
