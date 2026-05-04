# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Pure static HTML/CSS site for Octaive (octaive.ai) — a digital marketing agency. No build step, no framework, no package manager. Open any `.html` file directly in a browser.

## Development

No commands to run. To preview: open any `.html` file in a browser, or start a local server with:

```
python3 -m http.server 8000
```

To validate HTML: `npx html-validate *.html`

## Architecture

Single shared stylesheet, no JS framework, no templating engine.

**Files:**
- `index.html` — Home
- `about.html` — About
- `services.html` — Meet Octaive (services)
- `pricing.html` — Pricing
- `newsroom.html` — Newsroom article listing
- `contact.html` — Contact + form
- `css/main.css` — All styles
- `js/nav.js` — Mobile hamburger only (~15 lines)
- `images/` — Local assets (currently empty; live CDN URLs used as placeholders)

**Important:** Nav and footer HTML are copy-pasted into every page — there is no include/template system. When changing nav or footer, update all 6 files.

## CSS conventions

All design tokens are CSS custom properties at the top of `main.css` under `/* DESIGN TOKENS */`. Change colors, fonts, spacing, and radius there — nowhere else.

Key tokens:
- `--bg`, `--bg-card`, `--bg-section` — background layers
- `--accent` / `--accent-light` — purple accent (`#6c5ce7` / `#a29bfe`)
- `--text` / `--text-muted` — body text colors
- `--max-width: 1200px` — container width

Responsive breakpoints: `768px` (tablet/mobile), `1024px` (wide tablet). The mobile nav opens via `.nav-links.open` toggled by `js/nav.js`.

## Content notes

- Business name: Octaive | Legal entity: 8020.Marketing LLC
- Target market: companies earning $2M–$50M ARR
- Pricing tiers: Impact ($1,500/mo), Momentum ($3,000/mo), Dominion ($4,500/mo)
- Contact form `action=""` is intentionally blank — backend not yet wired
- Ad example placeholders in `index.html` (the 10-item `.ad-grid`) should be replaced with real `<img>` tags pointing to `/images/` once assets are downloaded
