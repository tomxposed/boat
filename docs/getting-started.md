# Getting Started with BOAT UI

BOAT UI is a production-ready, ultra-lightweight semantic HTML/CSS component library. Zero JavaScript. Zero dependencies. No build step required.

## Installation

### Option 1: Copy Files (Recommended)

Copy the project files to your project:

```
your-project/
├── index.css          ← main entry point
├── tokens.css
├── reset.css
├── typography.css
├── utilities.css
└── components/
    ├── grid.css
    ├── buttons.css
    ├── forms.css
    ├── cards.css
    ├── alerts.css
    ├── badges.css
    ├── modals.css
    └── navbar.css
```

Then link the single entry file in your HTML:

```html
<link rel="stylesheet" href="path/to/index.css">
```

### Option 2: Import Individual Files

Import only what you need:

```html
<link rel="stylesheet" href="tokens.css">
<link rel="stylesheet" href="reset.css">
<link rel="stylesheet" href="components/buttons.css">
<link rel="stylesheet" href="components/cards.css">
```

### Option 3: CSS `@import`

```css
@import url('path/to/index.css');
```

## Basic HTML Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My App</title>
  <!-- Optional: Inter font from Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <!-- BOAT UI -->
  <link rel="stylesheet" href="index.css">
</head>
<body>
  <!-- Skip link for accessibility -->
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

## Import Order

The CSS files must be imported in this order (already handled by `index.css`):

1. `tokens.css` — CSS custom properties (all other files depend on these)
2. `reset.css` — browser normalization
3. `typography.css` — heading and text styles
4. `utilities.css` — utility classes
5. `components/*.css` — individual components

## Browser Support

BOAT UI uses modern CSS features. Supported in:

| Browser | Version |
|---------|---------|
| Chrome  | 105+    |
| Firefox | 121+    |
| Safari  | 16.4+   |
| Edge    | 105+    |

Key features used:
- CSS Custom Properties (variables)
- `:target` pseudo-class (modals)
- `:has()` pseudo-class (body scroll lock, form validation)
- `backdrop-filter` (modal blur)
- CSS Grid & Flexbox
- `@media (prefers-color-scheme: dark)`

## Accessibility

BOAT UI is built with accessibility in mind:

- All interactive elements have visible focus rings (`:focus-visible`)
- Use semantic HTML5 elements (`<nav>`, `<header>`, `<main>`, `<article>`, `<button>`, etc.)
- Include `role` and `aria-*` attributes as shown in component examples
- The `.sr-only` utility class hides content visually while keeping it accessible to screen readers
- Include a skip link at the top of every page:

```html
<a href="#main-content" class="skip-link">Skip to main content</a>
```

## Progressive Enhancement

BOAT UI follows progressive enhancement principles:

1. **Content first** — semantic HTML works without CSS
2. **Style second** — CSS adds visual design
3. **Enhance optionally** — add JavaScript for enhanced interactions (focus trapping in modals, etc.)

The CSS-only modal and navbar work without JavaScript, but you can enhance them with JS for better accessibility (focus management, `aria-expanded` updates).
