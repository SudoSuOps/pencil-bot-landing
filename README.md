# pencil-bot-landing

Landing page for [pencilbot.ai](https://pencilbot.ai). Phase 1: one static page, no build step, no JavaScript.

## Layout

```
public/
  index.html            the page
  404.html              not-found page
  _headers              Cloudflare Pages security and cache headers
  robots.txt
  og.png                1200x630 share image
  favicon.svg, favicon-32.png, apple-touch-icon.png
  assets/css/site.css   all styles
  assets/img/           logo SVGs from the PencilBot brand kit
  assets/fonts/         self-hosted fonts (latin subsets, woff2)
```

## Deploy on Cloudflare Pages

1. Workers & Pages → Create → Pages → Connect to Git → pick this repository.
2. Production branch: `main`.
3. Framework preset: `None`. Build command: leave empty. Build output directory: `public`.
4. After the first deploy, add `pencilbot.ai` under Custom domains.

## Edit

Open `public/index.html` and change the text. To preview locally:

```
python3 -m http.server 8080 --directory public
```

Note: `_headers` sets a strict Content-Security-Policy that blocks inline styles and all scripts.
If you add a script, an inline `style` attribute or an outside resource, update that header too.

## Fonts

Archivo Black, DM Sans, IBM Plex Mono and Caveat Brush, all under the SIL Open Font License,
packaged by Fontsource. Logo SVGs use outlined shapes and need no fonts.

## Not included yet

- No contact link, form or analytics.
- The ledger example on the page is illustrative, not a real deal.
