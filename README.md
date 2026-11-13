# Reely website

Static site built from `reely-figma-motion-v3.2.html`. The original was one 16.5 MB file with every
font, image and video embedded inline. Here those are split into `assets/` so the page itself is
~180 KB and media loads only when it is needed, and can be cached.

- `index.html`: the page (markup, styles, motion scripts)
- `assets/fonts`, `assets/img`, `assets/video`: content-hashed files, safe to cache forever
- `_headers`: cache rules for Netlify / Cloudflare Pages

No build step. Serve it from any static host (Netlify, Vercel, Cloudflare Pages, GitHub Pages),
or locally with `python3 -m http.server` in this folder. Open it over http, not as a `file://`,
so the WebGL screens can read the video textures.

Motion turns off for visitors with "reduce motion" set, and via the switch in the footer.
