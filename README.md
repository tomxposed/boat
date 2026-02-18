# ⛵ BOAT UI

**A production-ready, ultra-lightweight semantic HTML/CSS component library.**  
Zero JavaScript. Zero dependencies. No build step. Just drop in the CSS and go.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![CSS only](https://img.shields.io/badge/CSS-only-blueviolet)
![Zero JS](https://img.shields.io/badge/JavaScript-none-green)
![Zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)

---

## ✨ Features

- **Zero JavaScript** — modals, dropdowns, and hamburger menus work with pure CSS
- **Zero dependencies** — no npm, no bundler, no build step required
- **Semantic HTML5** — `<button>`, `<nav>`, `<article>`, `<section>` throughout
- **CSS custom properties** — 200+ tokens for easy theming in one place
- **Mobile-first responsive** — 5 breakpoints, flexbox + CSS Grid layouts
- **Accessible** — ARIA roles, `:focus-visible` rings, skip links, `.sr-only`
- **Lightweight** — minimal CSS footprint, no unused styles

---

## 🚀 Quick Start

Copy the files to your project and link the single entry point:

```html
<link rel="stylesheet" href="index.css">
```

That's it. All components are ready to use.

### Basic page template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My App</title>
  <link rel="stylesheet" href="index.css">
</head>
<body>
  <a href="#main" class="skip-link">Skip to main content</a>

  <header class="navbar navbar-sticky" role="banner">
    <nav class="navbar-inner container" aria-label="Main navigation">
      <a href="/" class="navbar-brand">My App</a>
    </nav>
  </header>

  <main id="main">
    <div class="container section">
      <h1>Hello, World!</h1>
      <p class="text-lead">Welcome to my app.</p>
      <button type="button" class="btn btn-primary">Get Started</button>
    </div>
  </main>
</body>
</html>
```

---

## 📁 File Structure

```
boat/
├── index.css              ← Single entry point — import this
├── index.html             ← Live component showcase
├── tokens.css             ← Design tokens (CSS custom properties)
├── reset.css              ← Modern CSS reset
├── typography.css         ← Type scale & prose styles
├── utilities.css          ← Utility classes
├── components/
│   ├── accordion.css      ← CSS-only collapsible panels (<details>)
│   ├── alerts.css         ← Contextual feedback messages
│   ├── badges.css         ← Inline labels & status dots
│   ├── buttons.css        ← Button variants & states
│   ├── cards.css          ← Card layouts & variants
│   ├── dropdown.css       ← CSS-only dropdown menus
│   ├── forms.css          ← Inputs, selects, checkboxes, validation
│   ├── grid.css           ← Container, 12-col grid, CSS Grid
│   ├── modals.css         ← CSS-only dialogs via :target
│   ├── navbar.css         ← Responsive nav, breadcrumbs
│   ├── progress.css       ← Progress bars & circular progress
│   ├── sidebar.css        ← Sticky sidebar navigation layout
│   ├── skeleton.css       ← Loading placeholder shimmer
│   ├── spinner.css        ← Ring, grow & dots spinners
│   ├── table.css          ← Data tables with variants
│   ├── tabs.css           ← CSS-only tab panels (radio-based)
│   ├── toast.css          ← Notification toasts
│   └── tooltip.css        ← CSS-only tooltips via data-tooltip
└── docs/
    ├── getting-started.md
    ├── theming.md
    └── components.md
```

---

## 🧩 Components

| Component | Highlights |
|-----------|-----------|
| **Accordion** | CSS-only via `<details>`/`<summary>` · flush & separated variants |
| **Alert** | `info` `success` `warning` `danger` · dismissible (CSS-only) · banner |
| **Badge** | 6 color variants · solid · outline · pill · pulsing status dot · notification counter |
| **Button** | `primary` `secondary` `ghost` `outline` `danger` `success` · xs–xl · loading · icon · group |
| **Card** | Basic · interactive hover · stat · profile · horizontal · image · auto-fill grid |
| **Dropdown** | CSS-only via `:focus-within` · end/top alignment · divider · header · danger item |
| **Form** | Input · select · textarea · checkbox · radio · toggle switch · range · validation · input groups |
| **Grid** | 12-col flexbox grid · CSS Grid auto-fill · container · stack · sidebar layout |
| **Modal / Dialog** | sm/lg/xl/fullscreen · side drawer · alert dialog · body scroll lock via `:has()` |
| **Progress** | Bar with stripes/animation/indeterminate · stacked · circular (conic-gradient) |
| **Sidebar** | Sticky layout · active states · compact icon-only variant · responsive collapse |
| **Skeleton** | Shimmer animation · text/circle/rect/button shapes · card & list helpers |
| **Spinner** | Ring · grow/pulse · dots · size & color variants · overlay |
| **Table** | Striped · hover · bordered · compact/comfortable · sticky header · sortable · row states |
| **Tabs** | CSS-only radio-based switching · underline · pills · boxed · vertical |
| **Toast** | 6 position variants · color variants · progress bar · reduced-motion safe |
| **Tooltip** | CSS-only via `data-tooltip` · top/bottom/left/right placement |

---

## 🎨 Theming

All design decisions are CSS custom properties in `tokens.css`. Override any token after importing:

```css
/* my-theme.css — load after index.css */
:root {
  --color-primary-600: #7c3aed;   /* purple brand */
  --color-brand: var(--color-primary-600);
  --font-sans: 'Outfit', sans-serif;
  --radius-lg: 0.75rem;
}
```

See [`docs/theming.md`](docs/theming.md) for the full token reference.

---

## 🌐 Browser Support

| Browser | Version |
|---------|---------|
| Chrome  | 105+    |
| Firefox | 121+    |
| Safari  | 16.4+   |
| Edge    | 105+    |

Key CSS features used: custom properties, `:target`, `:has()`, `backdrop-filter`, CSS Grid, `@layer`.

---

## 📖 Documentation

| Guide | Description |
|-------|-------------|
| [Getting Started](docs/getting-started.md) | Installation, HTML template, import order |
| [Theming](docs/theming.md) | Overriding tokens, custom themes, scoped themes |
| [Components](docs/components.md) | Full HTML reference for every component |

Open `index.html` in any modern browser to see the live component showcase.

---

## 🤝 Contributing

1. Fork the repo
2. Make your changes in the relevant CSS file
3. Test in `index.html`
4. Open a pull request

Please keep changes focused — one component or feature per PR. Follow the existing code style (4-space indentation, CSS custom properties for all values).

---

## 📄 License

MIT © BOAT UI Contributors
