# ACS / UAB UI Kit Usage Instructions

## About the UI Kit

The ACS / UAB UI Kit is a Bootstrap-based theme and component guide for building consistent UAB web applications.

Bootstrap components are the foundation of the UI Kit. The UAB theme customizes Bootstrap colors, typography, focus states, spacing, and selected reusable patterns.

Use this UI Kit as the visual source of truth when styling ASP.NET MVC or ASP.NET Core MVC applications.

Do not use this UI Kit as a reason to rewrite application logic, change controllers, remove dependencies, or replace working functionality.

The UI Kit is for visual consistency, reusable components, accessibility, and responsive layout.

---

## Priority order

When creating or updating UI, use this priority order:

1. Existing ACS / UAB UI Kit component or documented pattern
2. Standard Bootstrap component
3. Bootstrap utility classes
4. Minimal reusable custom CSS only when the first three options are insufficient

Do not recreate standard Bootstrap components with custom HTML or CSS.

Do not recreate Bootstrap inputs, buttons, alerts, cards, modals, navbars, tabs, tables, or utilities.

---

## UI Kit technology

The UI Kit is designed to work with:

* Bootstrap 5.3 or later
* Bootstrap JavaScript Bundle
* Bootstrap Icons
* UAB Adobe Fonts
* `uab-theme.css`
* Existing application stylesheet: `site.css`

When applying this UI Kit to an existing application, inspect the app first and preserve existing dependencies.

Do not add duplicate Bootstrap references.

Do not remove existing JavaScript libraries unless explicitly approved.

Do not remove:

* jQuery
* jQuery Validation
* Unobtrusive Validation
* DataTables
* Bootstrap scripts
* Existing application-specific JavaScript

---

## Bootstrap guidance

ASP.NET MVC and ASP.NET Core MVC applications may already include Bootstrap.

Before adding or changing Bootstrap references:

* Inspect the existing layout.
* Inspect existing CSS references.
* Inspect existing script references.
* Check whether Bootstrap is already included locally, through CDN, or through bundles.
* Check which Bootstrap version is currently being used.
* Do not add duplicate Bootstrap CSS references.
* Do not add duplicate Bootstrap JavaScript references.
* Do not mix Bootstrap versions.
* Do not upgrade Bootstrap blindly in older ASP.NET MVC 5 / .NET Framework apps.

If Bootstrap is already present, preserve the existing setup when possible.

If Bootstrap must be updated to match the UI Kit, explain the reason before making the change.

For ASP.NET MVC 5 / .NET Framework applications, be extra careful with Bootstrap version changes because upgrading from Bootstrap 3 or 4 to Bootstrap 5 can affect markup, scripts, layout, and existing JavaScript behavior.

---

## Required UI Kit files

The UI Kit usually includes:

* `docs/acs-ui-kit.html`
* `docs/instructions.md`
* `css/uab-theme.css`
* `images/`

Use `acs-ui-kit.html` as the component reference.

Use `instructions.md` as the implementation rules.

Use `uab-theme.css` as the reusable theme stylesheet.

Use the `images` folder for official brand assets.

Do not create fake logos, placeholder logos, or invented brand assets.

---

## Recommended stylesheet order

When using Bootstrap 5.3, the preferred stylesheet order is:

```html
<link href="BOOTSTRAP_CSS_REFERENCE" rel="stylesheet">
<link rel="stylesheet" href="BOOTSTRAP_ICONS_REFERENCE">
<link rel="stylesheet" href="UAB_ADOBE_FONT_REFERENCE">
<link rel="stylesheet" href="UAB_THEME_CSS_REFERENCE">
<link rel="stylesheet" href="SITE_CSS_REFERENCE">
```

For ASP.NET Core MVC, this may look like:

```html
<link rel="stylesheet" href="~/lib/bootstrap/dist/css/bootstrap.min.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.13.1/font/bootstrap-icons.min.css">
<link rel="stylesheet" href="https://use.typekit.net/bwu2roe.css">
<link rel="stylesheet" href="~/css/uab-theme.css" asp-append-version="true">
<link rel="stylesheet" href="~/css/site.css" asp-append-version="true">
```

For ASP.NET MVC 5 / .NET Framework, this may look like:

```html
<link rel="stylesheet" href="@Url.Content("~/Content/bootstrap.min.css")">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.13.1/font/bootstrap-icons.min.css">
<link rel="stylesheet" href="https://use.typekit.net/bwu2roe.css">
<link rel="stylesheet" href="@Url.Content("~/Content/uab-theme.css")">
<link rel="stylesheet" href="@Url.Content("~/Content/site.css")">
```

For the UI Kit documentation page, this may look like:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.13.1/font/bootstrap-icons.min.css">
<link rel="stylesheet" href="https://use.typekit.net/bwu2roe.css">
<link rel="stylesheet" href="css/uab-theme.css">
<link rel="stylesheet" href="css/site.css">
```

Adapt paths to the target application’s existing folder structure.

Do not break existing CSS bundles.

Do not add duplicate Bootstrap references.

---

## JavaScript guidance

Use the Bootstrap JavaScript Bundle when Bootstrap 5 interactive components are required.

Place Bootstrap JavaScript before the closing `</body>` tag when possible.

For Bootstrap 5, this may look like:

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

Preserve existing app scripts.

Do not remove:

* jQuery
* jQuery Validation
* Unobtrusive Validation
* DataTables
* Existing app-specific JavaScript

Do not replace older Bootstrap script setups in ASP.NET MVC 5 apps without first checking compatibility.

Avoid duplicate or conflicting Bootstrap script references.

---

## CSS ownership rules

Use `uab-theme.css` for:

* UAB color variables
* Bootstrap theme overrides
* Reusable UAB utility classes
* Reusable UI Kit components
* Shared focus states
* Shared hover states
* Shared validation states
* Shared interaction states
* Components documented in the ACS / UAB UI Kit

Use `site.css` for:

* Application-specific layouts
* Page-specific adjustments
* Styles that should not be shared by every UAB application

Do not place reusable UI Kit component styles in `site.css`.

Do not place application-specific one-off styles in `uab-theme.css`.

When new CSS is required:

1. Confirm Bootstrap cannot already provide the behavior.
2. Confirm the UI Kit does not already provide the pattern.
3. Reuse existing UAB variables and utilities.
4. Add the smallest possible CSS.
5. Use `uab-theme.css` only for reusable UI Kit styles.
6. Use `site.css` only for application-specific styles.
7. Avoid hard-coded colors when an existing UAB CSS variable is available.
8. Avoid inline styles unless there is a small, justified exception.

---

## Bootstrap-first rules

Use standard Bootstrap components before creating custom components.

Do not create custom classes for:

* Spacing
* Layout
* Flexbox
* Grid
* Alignment
* Responsiveness

when Bootstrap utilities already exist.

Apply UAB theme classes and documented UAB patterns to Bootstrap components.

Do not wrap content in cards unless the requested layout or documented component specifically requires a card.

Forms should not automatically be wrapped in cards.

Use cards only when they represent a meaningful grouped container, summary panel, dashboard item, callout, or documented card pattern.

---

## Layout rules

Use the documented ACS / UAB layout patterns.

A standard application layout may include:

* UAB/ACS styled navbar
* UAB/ACS styled footer
* Main content area
* Responsive container
* Consistent spacing
* Accessible navigation
* Proper heading structure
* Main content landmark
* Skip link when appropriate

Use partial views for reusable layout sections when appropriate:

* `_Navbar.cshtml`
* `_Footer.cshtml`

Do not create unnecessary partials if the project structure does not need them.

### Default application layout structure

Use this default layout structure unless the application already has a better working layout:

```cshtml
<body class="d-flex flex-column min-vh-100">
    Navbar

    <main id="main-content" role="main" class="container flex-grow-1 py-4">
        @RenderBody()
    </main>

    Footer

    Scripts
</body>

Keep the navbar and footer outside the main container when they need full-width backgrounds.

Use the main content area as the flexible section so the footer stays at the bottom on short pages.

Prefer py-4 or similar vertical spacing on the main content area so the page content does not sit too close to the navbar or footer.

---

## Buttons

Use Bootstrap button classes with UAB theme overrides.

Prefer:

```html
<button type="button" class="btn btn-primary">Primary</button>
<a href="#" class="btn btn-outline-primary">Secondary</a>
```

Use documented UI Kit utility classes, such as press or motion effects, only when they are already defined in the theme.

Do not create custom button classes unless Bootstrap and the UI Kit are insufficient.

---

## Forms

Use standard Bootstrap form controls with UAB theme overrides.

Use:

* `form-label`
* `form-control`
* `form-select`
* `form-text`
* `input-group`
* `input-group-text`
* `form-check`
* `form-check-input`
* `form-check-label`
* `form-switch`
* `form-range`

Example:

```html
<form>
    <div class="row g-4">
        <div class="col-md-6">
            <label for="txtName" class="form-label fw-semibold">Name</label>
            <input type="text" class="form-control" id="txtName" name="Name" placeholder="Enter a name">
        </div>
        <div class="col-md-6">
            <label for="ddlDepartment" class="form-label fw-semibold">Department</label>
            <select class="form-select" id="ddlDepartment" name="Department">
                <option value="" selected disabled>Select a department</option>
                <option value="UAB IT">UAB IT</option>
                <option value="Print Services">Print Services</option>
            </select>
        </div>
    </div>
</form>
```

Preserve existing ASP.NET MVC form behavior:

* Form actions
* Routes
* Input names
* Input IDs
* Hidden fields
* Validation summaries
* Anti-forgery tokens
* Model binding
* Unobtrusive validation attributes
* JavaScript hooks used by existing scripts

Do not replace working forms with unrelated demo markup.

---

## Search fields

Use an input group with a Bootstrap Icon and a UAB primary button when a styled search field is needed.

```html
<form>
    <label for="txtSearch" class="form-label fw-semibold">Search</label>
    <div class="input-group">
        <span class="input-group-text">
            <i class="bi bi-search" aria-hidden="true"></i>
        </span>
        <input type="search" class="form-control" id="txtSearch" name="Search" placeholder="Search products or orders">
        <button type="submit" class="btn btn-primary">Search</button>
    </div>
</form>
```

---

## Selection controls

Use Bootstrap selection controls.

The UAB theme provides selected and focus states.

```html
<div class="form-check">
    <input class="form-check-input" type="checkbox" id="chkProof" name="IncludeProof">
    <label class="form-check-label" for="chkProof">Include a digital proof</label>
</div>

<div class="form-check">
    <input class="form-check-input" type="radio" name="DeliveryMethod" id="rdoPickup" value="Pickup" checked>
    <label class="form-check-label" for="rdoPickup">Pickup</label>
</div>

<div class="form-check form-switch">
    <input class="form-check-input" type="checkbox" role="switch" id="swtNotifications" name="Notifications" checked>
    <label class="form-check-label" for="swtNotifications">Email notifications</label>
</div>
```

---

## Range controls

Use the standard Bootstrap `form-range` component.

The UAB theme controls its selected color and focus state.

```html
<label for="rngPriority" class="form-label fw-semibold">Priority Level</label>
<input type="range" class="form-range" id="rngPriority" name="Priority" min="1" max="5" value="3">
```

---

## Validation

Use Bootstrap validation classes when compatible with the project:

* `is-valid`
* `is-invalid`
* `valid-feedback`
* `invalid-feedback`

Use `aria-describedby` when helper text or validation messages are associated with an input.

Do not remove existing server-side validation helpers.

Do not remove existing validation summaries.

Do not remove unobtrusive validation attributes.

---

## Attachment upload

Use the documented ACS / UAB attachment upload component when a styled file upload is required.

Available classes may include:

* `uab-file-upload`
* `uab-file-upload-input`
* `uab-file-upload-label`
* `uab-file-selection`

The component should:

* Preserve a native file input
* Support keyboard selection
* Include an associated label
* Display accepted file types and size limits
* Display the selected filename and size when JavaScript is available
* Provide an accessible remove button when needed
* Use UAB variables and theme utilities
* Avoid inline colors
* Avoid inaccessible clickable-only `<div>` elements

Do not replace the native file input with an inaccessible clickable `<div>`.

---

## Tables

Use standard Bootstrap responsive tables unless the UI Kit documents a more specific pattern.

Use DataTables only for advanced administrative lists requiring:

* Search
* Ordering
* Pagination
* Page-size controls

DataTables is optional and is not required for standard responsive tables.

If DataTables is already used in the application, preserve it.

When using DataTables:

* Use the Bootstrap-compatible DataTables styling that matches the app’s Bootstrap version.
* Disable ordering and searching for action columns.
* Preserve existing DataTables initialization logic unless an approved update is required.
* Do not combine the mobile table pattern with DataTables unless the UI Kit explicitly supports that integration.

If using the mobile table pattern, keep `data-label` attributes synchronized with table headers.

---

## Cards

Do not wrap content in cards by default.

Use cards only when they have a meaningful design purpose, such as:

* Dashboard summary item
* Grouped content panel
* Status summary
* Callout area
* Documented UI Kit card pattern

Do not use cards just to add borders around forms.

---

## Alerts and badges

Use Bootstrap alerts and badges with UAB theme overrides.

Do not create custom alert or badge components unless Bootstrap and the UI Kit are insufficient.

Use alerts for meaningful user-facing status messages.

Use badges for short statuses, categories, or labels.

---

## Icons

Use Bootstrap Icons when icons are needed.

Decorative icons should include:

```html
aria-hidden="true"
```

Do not use icons as the only way to communicate meaning.

Include accessible text for icon-only buttons.

---

## Accessibility rules

Preserve or improve accessibility.

Use:

* Semantic HTML
* Proper labels for form fields
* Associated labels using `for` and `id`
* `aria-describedby` for helper text and validation messages
* Accessible button text
* `aria-hidden="true"` for decorative icons
* Keyboard-accessible controls
* Responsive layouts that do not depend only on color or hover

Do not remove existing accessibility attributes.

Do not create inaccessible custom controls when a native control or Bootstrap component is available.

---

## HTML formatting rules

Follow compact Bootstrap documentation-style formatting.

* Keep HTML attributes on the same line unless the element becomes difficult to read.
* Do not add empty lines between every opening and closing tag.
* Use consistent indentation.
* Keep related elements together.
* Add spacing between logical component groups, not between every HTML element.
* Keep Razor syntax readable.
* Do not over-format existing files unnecessarily.

Preferred:

```html
<div class="container text-center">
    <div class="row align-items-start">
        <div class="col">
            One of three columns
        </div>
        <div class="col">
            One of three columns
        </div>
        <div class="col">
            One of three columns
        </div>
    </div>
</div>
```

Avoid:

```html
<div class="container text-center">

    <div class="row align-items-start">

        <div class="col">
            One of three columns
        </div>

    </div>

</div>
```

---

## Code examples

When generating documentation examples:

* Keep documentation-only wrappers separate from reusable component code.
* Do not include UI Kit documentation containers in copied application markup.
* Do not include `code-card` wrappers in application markup.
* Include the component’s functional wrapper, such as `<form>`, when required.
* Keep examples focused and reusable.
* Avoid one excessively large example when smaller independent examples are better.

---

## Code-generation process

Before writing code:

1. Inspect `uab-theme.css`, `site.css`, and the component documentation.
2. Determine whether the requested interface matches an existing UAB pattern.
3. If no UAB-specific pattern exists, use the standard Bootstrap component.
4. Use Bootstrap utilities for layout and spacing.
5. Do not add a card wrapper unless it has a meaningful design purpose.
6. Add reusable custom CSS to `uab-theme.css` only when Bootstrap and existing UAB classes are insufficient.
7. Add application-specific CSS to `site.css`.
8. Explain why new CSS is required before creating it.
9. Preserve accessibility and responsive behavior.
10. Follow the documented compact HTML formatting style.

---

## Final checklist

Before finishing UI work, verify:

* The existing Bootstrap setup was inspected before changes were made.
* Duplicate Bootstrap references were not introduced.
* Bootstrap versions were not mixed.
* Bootstrap components were not unnecessarily recreated.
* Bootstrap Icons are used correctly when needed.
* UAB fonts are preserved.
* `uab-theme.css` is loaded after Bootstrap.
* `site.css` is loaded after `uab-theme.css`.
* Existing scripts and dependencies were preserved.
* No unauthorized colors were introduced.
* No alternative design system was introduced.
* Existing UI Kit classes were reused.
* Forms were not unnecessarily wrapped in cards.
* Reusable styles were placed in `uab-theme.css`.
* Application-specific styles were placed in `site.css`.
* The layout is responsive.
* The markup is accessible.
* HTML follows the documented compact formatting style.
* Tables include synchronized `data-label` attributes when using the mobile table pattern.
* DataTables and the mobile table pattern were not combined without an approved integration.
* New CSS was avoided or minimized.
* Existing form behavior was preserved.
* Existing validation behavior was preserved.
* Existing JavaScript behavior was preserved.
