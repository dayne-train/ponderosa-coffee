# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About

Static single-page brand style guide for Ponderosa Coffee (Central Point, OR), deployed via GitHub Pages. No build step — edit `index.html` and `style.css` directly, then push.

**Live site:** `dayne-train.github.io/ponderosa-coffee`

## Deploying

```bash
git add .
git commit -m "your message"
git push
```

GitHub Pages rebuilds automatically on every push to `main`.

## Architecture

Two files:

- **`index.html`** — single page with sections: Color Palette, Color Pairings, Typography, Voice & Tone, Design Tokens
- **`style.css`** — all tokens and component styles; the `:root` block is the single source of truth

## Token system

All design values live in `:root` at the top of `style.css`:

- Colors: `--color-espresso` / `--coffee` / `--tan` / `--cream` (primary), `--forest` / `--sage` / `--mist` (accent)
- Semantic aliases: `--color-bg`, `--color-text`, `--color-text-muted`, `--color-border`, `--color-surface`
- Spacing: numeric scale (`--space-1` through `--space-24`) + named aliases (`--space-xs` through `--space-xl`)
- Layout: `--max-width: 960px` and `--gutter: var(--space-md)` (used for all horizontal margins)

## Width consistency rule

All full-width containers must constrain content with the same pattern:

```css
/* Outer element: no horizontal padding */
.site-header { padding: var(--space-xl) 0 var(--space-lg); }

/* Inner wrapper: apply the gutter */
.site-header__inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 var(--gutter);
}
```

`.page` uses `max-width` + `padding: var(--space-xl) var(--gutter)` directly (no inner wrapper needed since it isn't full-bleed). Nav and site-header both use the outer/inner pattern.

## Typeface

Fraunces variable serif (Google Fonts CDN). Brand setting: `font-variation-settings: 'SOFT' 0, 'WONK' 1` — applied via `--fvs` token. Elements using a different font (monospace code snippets) should explicitly reset with `font-variation-settings: normal`.

## Notable CSS patterns

- **Grain texture** — fixed SVG `feTurbulence` overlay at `opacity: 0.038`, `z-index: 9000`, pointer-events none
- **Ghost numerals** — `.principle::before { content: attr(data-num); }` reads from the element's `data-num` attribute
- **Entrance animations** — `@keyframes fadeUp` with `animation-delay` stagger on `.site-header__*` children and `section:nth-child(n)`
- **Header rings** — `::before` / `::after` on `.site-header` draw large concentric circle decorations (coffee-stain motif)
