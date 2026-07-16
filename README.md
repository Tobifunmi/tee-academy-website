<div align="center">

# 📚 Tee Academy

### *The Excellent Erudite Academy*

A clean, retro-tech, paper-textured marketing website for a technology education brand — built with plain HTML, CSS, and just enough JavaScript to be interesting.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![No Build Step](https://img.shields.io/badge/Build%20Step-None-D97757?style=flat-square)](#)
[![Dark Mode](https://img.shields.io/badge/Dark%20Mode-Supported-2b2620?style=flat-square)](#-dark-mode)
[![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)](#-license)

</div>

---

## ✨ Overview

**Tee Academy** is a five-page static website for a fictional (or very real) technology education company. It pairs an editorial, paper-grain aesthetic with a warm Anthropic-inspired orange accent — think *stationery catalog meets developer bootcamp*. No frameworks, no build tools, no dependencies beyond two Google Fonts. Clone it, open `index.html`, and it just works.

| | |
|---|---|
| 🎨 **Design language** | Warm paper texture, catalog "stamp" motifs, dashed rules, index-card tilts |
| 🌓 **Theming** | Full light + dark mode with a persistent, animated toggle |
| 📱 **Responsive** | Mobile-first breakpoints, collapsible nav, fluid type scale |
| ⚡ **Performance** | Zero JS frameworks, zero build step, two font families |
| ♿ **Accessible** | Semantic landmarks, visible focus states, `aria-current`, reduced-motion support |

---

## 🗂️ Site Map

```
tee-academy-website/
├── index.html          # Home — hero, value props, featured courses, CTA
├── courses.html        # Full course catalog with embedded video lessons
├── tutorials.html      # Bite-size skill-builder tutorials, grouped by track
├── blog.html           # Editorial blog grid — plain-language tech essays
├── about.html           # Mission, teaching philosophy, who we serve
├── styles.css           # Single shared stylesheet — all pages, both themes
├── favicon.png           # Site favicon (referenced in every <head>)
└── README.md             # You are here
```

Every page shares the same header, footer, and design system — only the `<main>` content changes — so the whole site is driven by **one** `styles.css` file.

---

## 🌓 Dark Mode

Tee Academy ships with a complete second theme, not just an inverted filter.

- **Toggle:** a circular sun/moon button lives in the header on every page, right next to the mobile menu button.
- **Persistence:** your choice is saved to `localStorage` (`tee-theme`) and restored on your next visit.
- **System-aware:** first-time visitors get the theme that matches their OS setting (`prefers-color-scheme`).
- **No flash of wrong theme:** an inline script in `<head>` sets the theme *before* the page paints, so there's no light-mode flicker before dark mode kicks in.
- **True re-tuning, not inversion:** the paper grain, card surfaces, rules, and orange accent are all individually recalibrated for dark backgrounds — the retro-tech feel holds up in both modes.

```js
// The whole mechanism, in short:
localStorage.getItem('tee-theme')     // read saved preference
document.documentElement.setAttribute('data-theme', 'dark' | 'light')
```

All theme colors are defined as CSS custom properties and swapped via a single `:root[data-theme="dark"]` override block in `styles.css` — no duplicated markup, no JS-driven style rewrites.

---

## 🎨 Design System

<table>
<tr>
<td valign="top" width="50%">

**Color palette**

| Token | Light | Dark |
|---|---|---|
| `--paper` | `#F6F1E7` | `#1B1712` |
| `--card` | `#FBF8F1` | `#24201A` |
| `--ink` | `#262119` | `#F2EAD9` |
| `--orange` | `#D97757` | `#E2916A` |
| `--orange-deep` | `#B95B3D` | `#F0A97D` |
| `--rule` | `#DCD1BC` | `#3C3327` |

</td>
<td valign="top" width="50%">

**Typography**

| Role | Typeface |
|---|---|
| Display / headings | [Fraunces](https://fonts.google.com/specimen/Fraunces) |
| Body / UI | [Archivo](https://fonts.google.com/specimen/Archivo) |

**Signature motifs**

- 🏷️ Rotated "stamp" eyebrow labels
- 📇 Ruled index-card hero graphic
- ┄┄ Dashed section dividers
- 🟧 Marker-style text highlights

</td>
</tr>
</table>

---

## 🚀 Getting Started

No installation, no `npm install`, no build pipeline. This is a static site.

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/tee-academy-website.git
cd tee-academy-website

# 2. Open it
open index.html          # macOS
start index.html          # Windows
xdg-open index.html       # Linux
```

**Prefer a local server?** (recommended for accurate relative-path behavior)

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Then visit `http://localhost:8000`.

---

## 🧩 Pages at a Glance

| Page | Purpose |
|---|---|
| **`index.html`** | Landing page — hero pitch, "why study here" value props, featured courses, closing CTA |
| **`courses.html`** | Long-form course catalog with embedded YouTube lessons and syllabus facts per course |
| **`tutorials.html`** | Short, single-sitting tutorials grouped into Web Development, Programming, and Data tracks |
| **`blog.html`** | Card-grid of editorial essays on tools, trends, and learning habits |
| **`about.html`** | Brand mission, three teaching principles, and who the academy serves |

---

## 🛠️ Tech Stack

- **HTML5** — semantic, hand-written, zero templating
- **CSS3** — custom properties, CSS Grid & Flexbox, `feTurbulence`/`feDisplacementMap`-based SVG paper grain, no preprocessor
- **Vanilla JavaScript** — ~20 lines total, for the mobile nav toggle and theme toggle
- **Google Fonts** — Fraunces + Archivo, loaded via `<link>` with `preconnect`

No React, no bundler, no package.json. It's meant to stay this simple.

---

## ♿ Accessibility Notes

- Landmarks (`<header>`, `<main>`, `<footer>`, `<nav>`) throughout
- `aria-current="page"` on the active nav link per page
- `aria-expanded` / `aria-controls` on the mobile menu button
- Visible, high-contrast `:focus-visible` outlines in the accent orange
- `prefers-reduced-motion` respected — animations and smooth-scroll disable automatically
- Icon-only theme toggle has a descriptive `aria-label`

---

## 📄 License

Released under the [MIT License](LICENSE). Use it, remix it, teach with it.

---

<div align="center">

**Tee Academy** · *The Excellent Erudite Academy*
Made with 🖋️ and a little too much attention to paper texture.

</div>
