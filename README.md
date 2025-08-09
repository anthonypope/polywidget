# Polymet Squarespace Widget — GitHub + jsDelivr

This kit lets you host the widget files on GitHub and serve them to Squarespace via **jsDelivr** (free CDN). No Squarespace file manager needed.

## 1) Create a GitHub repo
- Name it something like `polymet-sq-widget`
- Click **Add file → Upload files** and upload:
  - `polymet-widget.css`
  - `polymet-widget.js`
  - `embed_snippet_jsdelivr.html` (for your reference)

Commit the upload to the **main** branch.

## 2) Use jsDelivr URLs
Replace USERNAME/REPO in these URLs:
```
https://cdn.jsdelivr.net/gh/USERNAME/REPO@main/polymet-widget.css
https://cdn.jsdelivr.net/gh/USERNAME/REPO@main/polymet-widget.js
```
(Alternatively, create a GitHub release tag like `v1.0.0` and use `@v1.0.0` for immutable caching.)

## 3) Paste into Squarespace
Use a **Code Block** on your page and paste:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/USERNAME/REPO@main/polymet-widget.css">
<div id="polymet-root"></div>
<script src="https://cdn.jsdelivr.net/gh/USERNAME/REPO@main/polymet-widget.js"></script>
<script>
  window.Polymet.mount('#polymet-root', {
    // accent: '#111111',
    // endpoint: 'https://formspree.io/f/yourid', // overrides baked-in endpoint
    // mailto: 'info@atelier7llc.com'
  })
</script>
```

## Defaults
- Baked-in Formspree endpoint: **https://formspree.io/f/mnnzlpaw**
- To change it, either override via `endpoint:` in the init or edit `polymet-widget.js` and re-upload.
- Button color is `accent`, default `#111111`.
- Dependency-free (pure JS + CSS).