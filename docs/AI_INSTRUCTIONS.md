# UAB UI Kit — AI Development Instructions

You are building an application that must use the existing UAB UI Kit.

## Required technology

Use only:

* Bootstrap 5.3 or later
* Bootstrap Icons
* UAB Adobe Fonts
* `uab-theme.css`
* Existing application stylesheet: `site.css`

Required stylesheet order:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.13.1/font/bootstrap-icons.min.css">

<link rel="stylesheet" href="https://use.typekit.net/pqq8aix.css">

<link rel="stylesheet" href="css/uab-theme.css">

<link rel="stylesheet" href="css/site.css">
```

## Source of truth

The following files are the source of truth for UI implementation:

* `uab-theme.css`
* `site.css`
* The ACS UI Kit component documentation and examples

Before generating UI code, inspect these files and reuse the classes, variables, and component patterns already defined there.

## Strict styling rules

1. Do not create a new visual theme.
2. Do not introduce another CSS framework.
3. Do not use Tailwind, Material UI, Bulma, Foundation, or custom design systems.
4. Do not invent new CSS classes when an existing UAB UI Kit or Bootstrap class can accomplish the same result.
5. Do not use arbitrary colors or hard-coded hexadecimal colors.
6. Do not override the UAB color palette.
7. Do not use inline styles unless the existing UI Kit example requires them and no reusable utility exists.
8. Do not generate a separate component style that conflicts with `uab-theme.css`.
9. Use Bootstrap utilities for layout, spacing, alignment, display, sizing, and responsiveness.
10. Use the custom UAB classes for visual identity and component appearance.

## Existing component patterns

Use these patterns whenever the requested UI matches them.

### Typography

Use:

* `font-serif` for page titles and featured headings
* `font-sans` for body text and interface elements
* Bootstrap typography utilities such as:

  * `fw-bold`
  * `fw-semibold`
  * `text-dark`
  * `text-primary`
  * `text-secondary`

Example:

```html
<h1 class="font-serif fw-bold text-dark">Page Title</h1>
<p class="font-sans text-secondary">Supporting page description.</p>
```

### Buttons

Use Bootstrap semantic button classes together with `uab-press`.

Available patterns:

```html
<button class="btn btn-primary uab-press" type="button">Primary</button>
<button class="btn btn-outline-primary uab-press" type="button">Outline</button>
<button class="btn btn-success uab-press" type="button">Success</button>
<button class="btn btn-warning uab-press" type="button">Warning</button>
<button class="btn btn-danger uab-press" type="button">Danger</button>
<button class="btn btn-info uab-press" type="button">Info</button>
```

Do not create custom button colors.

### Alerts

Use Bootstrap alerts with `rounded-soft`.

```html
<div class="alert alert-success rounded-soft" role="alert">
    <strong>Success:</strong> The operation was completed.
</div>
```

Use semantic alert variants:

* `alert-primary`
* `alert-success`
* `alert-warning`
* `alert-danger`

### Badges

Use the existing soft badge classes:

* `badge-soft-primary`
* `badge-soft-success`
* `badge-soft-warning`
* `badge-soft-danger`
* `badge-soft-info`
* `badge-pill`

Example:

```html
<span class="badge badge-pill badge-soft-success">
    <i class="bi bi-check-circle me-1" aria-hidden="true"></i>
    Completed
</span>
```

### Icon circles

Use:

* `uab-icon-circle`
* Existing UAB background utilities
* Bootstrap Icons

Available background patterns include:

* `bg-uab-evergreen-10`
* `bg-uab-success-bg`
* `bg-uab-warning-bg`
* `bg-uab-info-bg`
* `bg-uab-danger-bg`

Example:

```html
<div class="uab-icon-circle bg-uab-success-bg">
    <i class="bi bi-check-circle text-success" aria-hidden="true"></i>
</div>
```

### Cards and containers

Prefer Bootstrap cards and utilities.

Use existing visual utilities such as:

* `rounded-4`
* `rounded-soft`
* `shadow-sm`
* `border-soft`
* `bg-white`
* `border-0`

Do not create a new card design unless the existing UI Kit has no matching pattern.

### Navigation tabs

Use the existing `uab-tab` class with Bootstrap tabs.

```html
<ul class="nav" role="tablist">
    <li class="nav-item" role="presentation">
        <button class="nav-link uab-tab active"
                data-bs-toggle="tab"
                data-bs-target="#example-pane"
                type="button"
                role="tab">
            Example
        </button>
    </li>
</ul>
```

### Tables

Use this responsive table pattern:

```html
<div class="table-container table-responsive table-column-mobile p-2 pb-0 bg-white rounded-4 shadow-sm border-soft">

    <table class="table table-hover small align-middle">
        ...
    </table>

</div>
```

Every table cell must include a `data-label` value matching its column heading:

```html
<td class="align-middle text-wrap py-2" data-label="Customer">
    Jane Smith
</td>
```

Use soft badges for table statuses and Bootstrap Icons for row actions.

### Navbar

Use:

* Bootstrap navbar structure
* `navbar-dark`
* `bg-uab-green`
* Bootstrap Icons
* Existing responsive collapse behavior

Do not create a different navbar color or style.

### Footer

Use the existing responsive UAB footer pattern.

Use:

* `bg-uab-dragon-green`
* White UAB logos
* Existing institutional links
* Existing mobile and desktop layouts

Do not simplify or replace the required institutional footer content without being explicitly instructed to do so.

## Accessibility requirements

All generated UI must:

* Use semantic HTML
* Include `aria-label` where icon-only buttons need accessible names
* Include `aria-hidden="true"` on decorative icons
* Use `scope="col"` for table headers
* Use proper button types
* Support keyboard navigation
* Preserve visible focus states
* Maintain sufficient contrast
* Use `alt` text for meaningful images
* Use Bootstrap responsive behavior
* Avoid using color as the only indication of status

## Responsive requirements

Use Bootstrap breakpoints and utilities.

The UI must work on:

* Mobile
* Tablet
* Desktop

Do not write fixed-width layouts that cause horizontal scrolling.

Prefer:

* Bootstrap grid
* Flex utilities
* Responsive containers
* `flex-wrap`
* `table-responsive`
* Existing mobile table pattern

## Code-generation process

Before writing code:

1. Identify whether the requested interface matches an existing UI Kit component.
2. Reuse that component's HTML structure and classes.
3. Use Bootstrap utilities for layout changes.
4. Add custom CSS only when no existing class or Bootstrap utility can meet the requirement.
5. When custom CSS is necessary, keep it minimal and place it in `site.css`.
6. Explain any new CSS class before creating it.

## Output requirements

When generating UI code:

* Return complete, usable markup.
* Preserve the project's existing formatting style.
* Keep HTML attributes on the same line unless the element becomes difficult to read.
* Do not omit accessibility attributes.
* Do not replace existing UAB classes with generic custom classes.
* Do not generate placeholder CSS for styles that already exist.
* Mention which existing UI Kit components were reused.
* Clearly identify any new CSS that was unavoidable.

## Final validation checklist

Before returning code, verify:

* Bootstrap 5.3+ is used.
* Bootstrap Icons are used correctly.
* UAB fonts are preserved.
* `uab-theme.css` is preserved.
* No unauthorized color was introduced.
* No alternative design system was introduced.
* Existing UAB component classes were reused.
* The layout is responsive.
* The markup is accessible.
* Tables include synchronized `data-label` attributes.
* New CSS was avoided or minimized.
