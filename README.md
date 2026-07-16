# robertyoung.ie

Personal site for Robert Young, Technical Lead &amp; Software Engineer.

A single, hand-built static page. No framework and no build step. Design
direction: a two-column "terminal" layout, with a sticky identity/nav
sidebar, a scrolling content column, a single amber signal colour and IBM Plex
typography.

## Structure

| File | Purpose |
| --- | --- |
| `index.html` | The page |
| `styles.css` | All styling (design tokens in `:root`, layout, responsive, CSS-only motion) |
| `fonts/` | Self-hosted IBM Plex woff2 (latin subset) |
| `favicon.svg` | Monogram favicon |
| `og.png` | 1200×630 social share card |
| `CNAME` | Custom domain (`www.robertyoung.ie`) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll) |
| `robots.txt`, `sitemap.xml` | Basic SEO |

## Theming

Colour and type tokens live in the `:root` block at the top of `styles.css`.
Dark is the default; a `@media (prefers-color-scheme: light)` block overrides
the same tokens.

Light mode is **not** an inversion. The amber (`#e0a64a`) only reaches 2:1 on a
light background, so light mode uses a darker amber (`#8a5a12`). The amber chips
(`.mark`, `.skip-link`) therefore take their text colour from `--on-accent`,
which flips from near-black to near-white — near-black on the darker amber would
fail WCAG at 2.9:1. Every text/background token pair clears WCAG AA (4.5:1) in
both modes; re-check that if you retheme.

## Fonts

IBM Plex is self-hosted from `fonts/` — no third-party request, no visitor IP
sent to Google. The files are the same latin-subset woff2 Google serves. Sans is
a **variable** font, so one file covers every weight (100–700); Mono ships as
three static weights. The system fallback stacks in `--mono` / `--sans` still
apply if the files fail to load.

## Analytics

[GoatCounter](https://www.goatcounter.com/) — no cookies, no personal data, so
no consent banner. The snippet at the bottom of `index.html` counts pageviews; a
delegated `click` listener next to it counts outbound link clicks as events, and
is guarded so a blocked counter can never break the page.

## Develop

Plain static files. Open `index.html`, or serve locally:

```sh
python3 -m http.server
# → http://localhost:8000
```

## Deploy

Hosted on GitHub Pages from the default branch. Pushing to `master` publishes
to <https://www.robertyoung.ie>.
