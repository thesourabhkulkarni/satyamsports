# Sports Carousel Component

A mobile-responsive, infinite-loop, drag/swipe-able card carousel, built so
you can drop it straight into an **existing** `index.html` without it
clashing with your site's own CSS or JS.

## Files

```
sports-carousel.css   ← all styles, scoped under .sports-carousel-section
sports-carousel.js    ← all behavior, auto-initializes on page load
snippet.html          ← the HTML block to paste into your page
assets/               ← the 8 jpg images, referenced by relative path
demo.html             ← standalone page showing it all wired together
```

## How to add it to your existing site

1. **Copy these 4 items** into your project, keeping them next to each
   other (same folder as your `index.html`, or adjust the paths below to
   match wherever you put them):
   - `sports-carousel.css`
   - `sports-carousel.js`
   - the `assets/` folder

2. **In your existing `index.html`'s `<head>`**, add:
   ```html
   <link rel="stylesheet" href="sports-carousel.css">
   ```

3. **Right before your closing `</body>` tag**, add:
   ```html
   <script src="sports-carousel.js"></script>
   ```

4. **Paste the contents of `snippet.html`** anywhere inside your `<body>`
   where you want the carousel to appear (e.g. a homepage section).

That's it — the script finds any `.sports-carousel-section` on the page
when it loads and wires up the buttons, drag/swipe, infinite loop, and
dots automatically.

## Notes

- **Scoped, won't collide**: every CSS rule lives under
  `.sports-carousel-section`, and the JS is a single IIFE that only
  touches elements inside that section — safe to drop into a page that
  already has its own styles and scripts.
- **Multiple carousels on one page** are supported — just paste the
  snippet more than once; each instance initializes independently.
- **Changing the cards**: edit the `DEFAULT_CARDS` array at the top of
  `sports-carousel.js`, or set a `data-items='[...]'` JSON attribute
  directly on the `<section class="sports-carousel-section" ...>` tag to
  override the cards for one specific instance without touching the JS
  file.
- **Links**: each card's `href` is currently a placeholder anchor
  (`#cricket`, `#football`, etc.) — update the `href` values in the
  `DEFAULT_CARDS` array to your real category page URLs.
- **Images**: swap the jpgs in `assets/` for your own — just keep the
  same filenames, or update the `img` path per card if you rename them.
