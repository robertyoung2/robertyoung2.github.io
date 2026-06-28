# robertyoung.ie

Personal site for Robert Young, Technical Lead &amp; Software Engineer.

A single, hand-built static page. No framework and no build step. Design
direction: a dark, two-column "terminal" layout, with a sticky identity/nav
sidebar, a scrolling content column, a single amber signal colour and IBM Plex
typography.

## Structure

| File | Purpose |
| --- | --- |
| `index.html` | The page |
| `styles.css` | All styling (design tokens in `:root`, layout, responsive, CSS-only motion) |
| `favicon.svg` | Monogram favicon |
| `CNAME` | Custom domain (`www.robertyoung.ie`) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll) |
| `robots.txt`, `sitemap.xml` | Basic SEO |

Fonts (IBM Plex Mono + Sans) load from Google Fonts; the system fallback stacks
in `--mono` / `--sans` keep it readable if they don't. The colour and type tokens
all live at the top of `styles.css`, so re-theming (or adding a light mode) is a
matter of editing the `:root` block.

## Develop

Plain static files. Open `index.html`, or serve locally:

```sh
python3 -m http.server
# → http://localhost:8000
```

## Deploy

Hosted on GitHub Pages from the default branch. Pushing to `master` publishes
to https://www.robertyoung.ie.
