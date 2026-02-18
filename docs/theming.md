# Theming Guide

BOAT UI uses CSS custom properties (variables) for all design decisions. Override any token to customize the entire system — no build step required.

## How Theming Works

All tokens are defined on `:root` in `tokens.css`. Override them in your own stylesheet **after** importing BOAT UI:

```css
/* my-theme.css */
:root {
  --color-primary-600: #7c3aed;  /* Purple instead of Indigo */
  --color-primary-700: #6d28d9;
  --color-brand: var(--color-primary-600);
  --radius-lg: 0.75rem;          /* Rounder corners */
  --font-sans: 'Outfit', sans-serif;
}
```

```html
<link rel="stylesheet" href="index.css">
<link rel="stylesheet" href="my-theme.css">  <!-- overrides go after -->
```

## Key Tokens to Override

### Brand Color

```css
:root {
  /* Change the primary brand color */
  --color-primary-600: #dc2626;  /* Red */
  --color-primary-700: #b91c1c;
  --color-primary-400: #f87171;
  --color-primary-100: #fee2e2;
  --color-primary-50:  #fef2f2;

  /* Semantic tokens automatically follow */
  --color-brand:        var(--color-primary-600);
  --color-brand-hover:  var(--color-primary-700);
  --color-brand-subtle: var(--color-primary-50);
}
```

### Typography

```css
:root {
  --font-sans: 'Outfit', 'Nunito', sans-serif;
  --font-mono: 'Fira Code', monospace;

  /* Scale */
  --text-base: 1rem;      /* Adjust base font size */
  --text-lg:   1.125rem;
}
```

### Border Radius

```css
/* Sharp / enterprise look */
:root {
  --radius-sm:   2px;
  --radius-md:   4px;
  --radius-lg:   6px;
  --radius-xl:   8px;
  --radius-2xl:  10px;
}

/* Very rounded / friendly look */
:root {
  --radius-sm:   0.5rem;
  --radius-md:   0.75rem;
  --radius-lg:   1rem;
  --radius-xl:   1.25rem;
  --radius-2xl:  1.5rem;
}
```

### Spacing Scale

```css
/* Tighter spacing */
:root {
  --space-4: 0.875rem;   /* 14px instead of 16px */
  --space-6: 1.25rem;    /* 20px instead of 24px */
}
```

## Dark Mode

### Automatic (System Preference)

Dark mode is enabled automatically via `@media (prefers-color-scheme: dark)`. No configuration needed.

### Manual Toggle (CSS-only)

Add the `.dark` class to `<html>` to force dark mode:

```html
<html class="dark">
```

The demo page uses a checkbox + JavaScript to toggle the class:

```html
<input type="checkbox" id="dark-toggle" hidden
       onchange="document.documentElement.classList.toggle('dark', this.checked)">
<label for="dark-toggle">Toggle dark mode</label>
```

Or use the built-in `.dark-mode-input` / `.dark-mode-label` classes for a styled toggle switch.

### Custom Dark Mode Overrides

```css
html.dark {
  --color-brand: #818cf8;           /* Lighter primary in dark mode */
  --color-brand-hover: #a5b4fc;
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-brand: #818cf8;
  }
}
```

## Creating a Complete Custom Theme

```css
/* themes/ocean.css */
@import url('../index.css');

:root {
  /* Ocean blue palette */
  --color-primary-50:  #eff6ff;
  --color-primary-100: #dbeafe;
  --color-primary-200: #bfdbfe;
  --color-primary-300: #93c5fd;
  --color-primary-400: #60a5fa;
  --color-primary-500: #3b82f6;
  --color-primary-600: #2563eb;
  --color-primary-700: #1d4ed8;
  --color-primary-800: #1e40af;
  --color-primary-900: #1e3a8a;

  /* Typography */
  --font-sans: 'Inter', system-ui, sans-serif;

  /* Rounder corners */
  --radius-lg: 0.625rem;
  --radius-xl: 0.875rem;
  --radius-2xl: 1.125rem;
}
```

## Scoped Themes

Apply a theme to a specific section only:

```html
<section class="dark-section">
  <button class="btn btn-primary">Themed Button</button>
</section>
```

```css
.dark-section {
  --color-bg:      #0f172a;
  --color-surface: #1e293b;
  --color-text:    #f8fafc;
  --color-border:  #334155;
  background-color: var(--color-bg);
  color: var(--color-text);
  padding: 2rem;
}
```

## Token Reference

| Token | Default | Description |
|-------|---------|-------------|
| `--color-brand` | `#4f46e5` | Primary action color |
| `--color-bg` | `#f8fafc` | Page background |
| `--color-surface` | `#ffffff` | Card/panel surface |
| `--color-text` | `#0f172a` | Body text |
| `--color-border` | `#e2e8f0` | Default border |
| `--font-sans` | Inter, system-ui | Body font |
| `--space-4` | `1rem` | Base spacing unit |
| `--radius-lg` | `0.5rem` | Default border radius |
| `--shadow-md` | `...` | Default shadow |
| `--transition-base` | `200ms ease-in-out` | Default transition |
