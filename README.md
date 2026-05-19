# ponderosa coffee — brand style guide

A self-hosted brand reference for Ponderosa Coffee, built as a single-page static site and deployed via GitHub Pages.

**Live site → [dayne-train.github.io/ponderosa-coffee](https://dayne-train.github.io/ponderosa-coffee/)**

---

## about ponderosa coffee

Ponderosa Coffee is a small-batch specialty coffee shop rooted in Central Point, Oregon — southern Oregon's Rogue Valley. We believe in good coffee, real community, and the quiet of the outdoors. Our beans are sourced from [Mythical Coffee](https://mythicalcoffee.com) in Gilbert, AZ.

**Location** — Central Point, OR  
**Contact** — [hello@ponderosa.coffee](mailto:hello@ponderosa.coffee)  
**Instagram** — [@ponderosa_coffee](https://instagram.com/ponderosa_coffee)

---

## what's in this guide

| Section | What it covers |
|---|---|
| **Colors** | Full palette with hex values and CSS variable names |
| **Pairings** | Approved color combinations with WCAG contrast notes |
| **Typography** | Fraunces type scale — display through caption |
| **Voice & Tone** | Brand personality, writing principles, do/don't copy examples |
| **Tokens** | Copy-paste CSS custom properties for use in any project |

---

## files

```
ponderosa-coffee/
├── index.html    — styleguide page
└── style.css     — all tokens and component styles
```

All tokens live in the `:root` block at the top of `style.css`. That's the single source of truth for colors, spacing, type scale, radius, shadows, and transitions.

---

## core tokens (quick ref)

```css
/* Primary colors */
--color-espresso:  #2c1e0f;
--color-coffee:    #836e48;
--color-tan:       #c4a878;
--color-cream:     #fff6e5;

/* Accent — Pine & Sage */
--color-forest:    #4a7a5a;
--color-sage:      #749e83;
--color-mist:      #b8d0c3;

/* Typeface */
--font-display: 'Fraunces', serif;
--fvs:          'SOFT' 0, 'WONK' 1;
```

---

## deploying changes

```bash
git add .
git commit -m "your message"
git push
```

GitHub Pages rebuilds automatically on every push to `main`.

---

*made with care in southern oregon*
