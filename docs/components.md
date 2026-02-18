# Component Reference

Quick reference for all BOAT UI components — HTML structure, modifier classes, and accessibility notes.

---

## Buttons

```html
<!-- Variants -->
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-ghost">Ghost</button>
<button type="button" class="btn btn-outline">Outline</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-success">Success</button>
<a href="#" class="btn btn-link">Link</a>

<!-- Sizes: btn-xs, btn-sm, (default), btn-lg, btn-xl -->
<button class="btn btn-primary btn-lg">Large</button>

<!-- States -->
<button class="btn btn-primary btn-loading" aria-label="Saving…">Save</button>
<button class="btn btn-primary" disabled>Disabled</button>

<!-- Icon button -->
<button class="btn btn-icon btn-secondary" aria-label="Settings">⚙</button>

<!-- Full width -->
<button class="btn btn-primary btn-block">Full Width</button>

<!-- Group -->
<div class="btn-group" role="group" aria-label="Actions">
  <button class="btn btn-secondary">A</button>
  <button class="btn btn-secondary">B</button>
  <button class="btn btn-secondary">C</button>
</div>
```

**Accessibility:** Always use `<button type="button">` for actions. Use `<a href>` only for navigation. Add `aria-label` to icon buttons.

---

## Forms

```html
<!-- Form group -->
<div class="form-group">
  <label class="form-label required" for="name">Full Name</label>
  <input type="text" id="name" class="form-control" placeholder="John Doe">
  <span class="form-hint">As it appears on your ID.</span>
</div>

<!-- Validation states -->
<input class="form-control is-valid" value="valid@email.com">
<input class="form-control is-invalid" value="bad-input">
<span class="form-error">Please enter a valid value.</span>
<span class="form-success-msg">Looks good!</span>

<!-- Select -->
<select class="form-select">
  <option>Choose…</option>
  <option>Option A</option>
</select>

<!-- Checkbox -->
<label class="form-check">
  <input type="checkbox" class="form-check-input" id="agree">
  <span class="form-check-label">I agree to the terms</span>
</label>

<!-- Radio -->
<label class="form-check">
  <input type="radio" name="plan" class="form-check-input" value="pro">
  <span class="form-check-label">Pro Plan</span>
</label>

<!-- Toggle switch -->
<label class="form-switch">
  <input type="checkbox" class="form-switch-input" checked>
  <span class="form-check-label">Enable feature</span>
</label>

<!-- Input group -->
<div class="input-group">
  <span class="input-group-text">$</span>
  <input type="number" class="form-control" placeholder="0.00">
  <span class="input-group-text">USD</span>
</div>

<!-- Textarea -->
<textarea class="form-control" rows="4" placeholder="Your message…"></textarea>

<!-- Range -->
<input type="range" class="form-range" min="0" max="100" value="50">
```

**Accessibility:** Always pair `<label>` with `for`/`id`. Use `aria-describedby` to link hint/error text to inputs. Mark required fields with `required` attribute.

---

## Cards

```html
<!-- Basic card -->
<article class="card">
  <div class="card-header">
    <h3 class="card-title">Title</h3>
  </div>
  <div class="card-body">
    <p>Content goes here.</p>
  </div>
  <div class="card-footer">
    <button class="btn btn-primary btn-sm">Action</button>
  </div>
</article>

<!-- Image card -->
<article class="card">
  <img src="photo.jpg" alt="Description" class="card-img-top">
  <div class="card-body">
    <h3 class="card-title">Image Card</h3>
  </div>
</article>

<!-- Interactive (link) card -->
<a href="/detail" class="card card-interactive">
  <div class="card-body">Content</div>
</a>

<!-- Stat card -->
<article class="card">
  <div class="card-stat">
    <span class="card-stat-label">Revenue</span>
    <span class="card-stat-value">$12,450</span>
    <span class="card-stat-change positive">+8.2%</span>
  </div>
</article>

<!-- Card group (auto-fill grid) -->
<div class="card-group">
  <article class="card">…</article>
  <article class="card">…</article>
  <article class="card">…</article>
</div>
```

**Modifiers:** `card-flat`, `card-elevated`, `card-outlined`, `card-filled`, `card-primary/success/warning/danger`, `card-horizontal`

---

## Alerts

```html
<div class="alert alert-info" role="note">
  <span class="alert-icon">ℹ</span>
  <div class="alert-content">
    <p class="alert-title">Info</p>
    <p>Informational message.</p>
  </div>
</div>

<!-- Variants: alert-info, alert-success, alert-warning, alert-danger, alert-neutral -->

<!-- Dismissible (CSS-only) -->
<div class="alert alert-success alert-dismissible" role="status">
  <input type="checkbox" id="dismiss-1" class="alert-dismiss-input">
  <span class="alert-icon">✓</span>
  <div class="alert-content">Message here.</div>
  <label for="dismiss-1" class="alert-dismiss-btn" aria-label="Dismiss">✕</label>
</div>

<!-- Banner (full-width) -->
<div class="alert alert-warning alert-banner" role="alert">
  ⚠ Maintenance scheduled Sunday 2–4 AM UTC.
</div>

<!-- Accent border -->
<div class="alert alert-danger alert-accent" role="alert">
  Error message with left accent border.
</div>
```

**Accessibility:** Use `role="alert"` for urgent messages (auto-announced by screen readers). Use `role="status"` for non-urgent updates. Use `role="note"` for informational content.

---

## Badges

```html
<!-- Inline badge -->
<span class="badge badge-primary">New</span>
<span class="badge badge-success">Active</span>
<span class="badge badge-warning">Beta</span>
<span class="badge badge-danger">Error</span>
<span class="badge badge-info">Info</span>
<span class="badge badge-neutral">Draft</span>

<!-- Pill shape -->
<span class="badge badge-pill badge-primary">12</span>

<!-- Solid fill -->
<span class="badge badge-solid-primary">Primary</span>

<!-- Outline -->
<span class="badge badge-outline badge-danger">Deprecated</span>

<!-- Sizes: badge-sm, (default), badge-lg -->

<!-- Status dot -->
<span class="badge-dot badge-dot-success badge-dot-pulse"></span> Online

<!-- Notification counter -->
<div class="badge-container">
  <button class="btn btn-icon btn-secondary" aria-label="Notifications">🔔</button>
  <span class="badge-notification badge-solid-danger">3</span>
</div>
```

---

## Modals

```html
<!-- Trigger link -->
<a href="#my-modal" class="btn btn-primary">Open Modal</a>

<!-- Modal (place at end of <body>) -->
<div id="my-modal" class="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <a href="#" class="modal-backdrop" aria-label="Close modal"></a>
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h2 id="modal-title" class="modal-title">Modal Title</h2>
        <a href="#" class="btn-close" aria-label="Close modal"></a>
      </div>
      <div class="modal-body">
        <p>Modal content here.</p>
      </div>
      <div class="modal-footer">
        <a href="#" class="btn btn-secondary">Cancel</a>
        <a href="#" class="btn btn-primary">Confirm</a>
      </div>
    </div>
  </div>
</div>
```

**Size modifiers:** `modal-sm`, `modal-lg`, `modal-xl`, `modal-fullscreen`  
**Drawer:** Add `modal-drawer` (right) or `modal-drawer modal-drawer-left` (left)  
**Alert dialog:** Add `modal-alert` for centered confirmation dialogs

**Accessibility note:** CSS-only modals don't trap focus. For full WCAG 2.1 compliance, add this small JS enhancement:

```javascript
document.querySelectorAll('.modal').forEach(modal => {
  modal.addEventListener('transitionend', () => {
    if (location.hash === '#' + modal.id) {
      modal.querySelector('[tabindex="-1"], button, a, input').focus();
    }
  });
});
```

---

## Navbar

```html
<header class="navbar navbar-sticky" role="banner">
  <nav class="navbar-inner container" aria-label="Main navigation">
    <a href="/" class="navbar-brand">Brand</a>

    <!-- Mobile toggle (CSS-only) -->
    <input type="checkbox" id="nav-toggle" class="navbar-toggle-input" aria-hidden="true">
    <label for="nav-toggle" class="navbar-toggle" aria-label="Toggle navigation">
      <span class="navbar-toggle-bar"></span>
      <span class="navbar-toggle-bar"></span>
      <span class="navbar-toggle-bar"></span>
    </label>

    <div class="navbar-collapse">
      <ul class="navbar-nav" role="list">
        <li><a href="/" class="nav-link active" aria-current="page">Home</a></li>
        <li><a href="/about" class="nav-link">About</a></li>
        <!-- Dropdown -->
        <li>
          <div class="nav-dropdown">
            <a href="#" class="nav-link nav-dropdown-toggle">Products</a>
            <ul class="nav-dropdown-menu" role="list">
              <li><a href="/product-a" class="nav-dropdown-item">Product A</a></li>
              <li><a href="/product-b" class="nav-dropdown-item">Product B</a></li>
              <li class="nav-dropdown-divider" role="separator"></li>
              <li><a href="/all" class="nav-dropdown-item">View All</a></li>
            </ul>
          </div>
        </li>
      </ul>
      <div class="navbar-actions">
        <a href="/login" class="btn btn-secondary btn-sm">Log in</a>
        <a href="/signup" class="btn btn-primary btn-sm">Sign up</a>
      </div>
    </div>
  </nav>
</header>
```

**Themes:** `navbar-dark`, `navbar-transparent`  
**Position:** `navbar-sticky` (sticky top)

---

## Grid

```html
<!-- Container -->
<div class="container">…</div>
<div class="container-fluid">…</div>

<!-- 12-column flexbox grid -->
<div class="row">
  <div class="col-12 col-md-8">Main content</div>
  <div class="col-12 col-md-4">Sidebar</div>
</div>

<!-- CSS Grid auto-fill -->
<div class="grid-auto-sm">  <!-- min 16rem columns -->
  <div class="card">…</div>
  <div class="card">…</div>
  <div class="card">…</div>
</div>

<!-- Fixed grid -->
<div class="grid-3">  <!-- 3 columns, responsive -->
  <div>…</div>
  <div>…</div>
  <div>…</div>
</div>

<!-- Stack (vertical spacing) -->
<div class="stack-4">
  <p>Spaced by 1rem</p>
  <p>Spaced by 1rem</p>
</div>
```

**Breakpoints:** `col-sm-*` (≥640px), `col-md-*` (≥768px), `col-lg-*` (≥1024px), `col-xl-*` (≥1280px)

---

## Navigation Extras

```html
<!-- Breadcrumb -->
<nav aria-label="Breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="/">Home</a></li>
    <li class="breadcrumb-item"><a href="/docs">Docs</a></li>
    <li class="breadcrumb-item active" aria-current="page">Components</li>
  </ol>
</nav>

<!-- Tabs -->
<nav class="tabs" role="tablist" aria-label="Section tabs">
  <a href="#tab-1" class="tab-link active" role="tab" aria-selected="true">Tab 1</a>
  <a href="#tab-2" class="tab-link" role="tab" aria-selected="false">Tab 2</a>
  <a href="#tab-3" class="tab-link" role="tab" aria-selected="false">Tab 3</a>
</nav>
```
