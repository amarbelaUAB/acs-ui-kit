## About the UI Kit

The UAB UI Kit is a Bootstrap 5.3 theme and component guide for building consistent UAB applications.

Bootstrap components are the foundation of the UI Kit. The UAB theme customizes Bootstrap colors, typography, focus states, and selected reusable patterns.

Do not recreate standard Bootstrap components with custom HTML or CSS.

Use this priority order:

1. Existing UAB UI Kit component or documented pattern
2. Standard Bootstrap 5.3 component
3. Bootstrap utility classes
4. Minimal reusable custom CSS only when the first three options are insufficient

---

## Required technology

Use only:

* Bootstrap 5.3 or later
* Bootstrap JavaScript Bundle
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

Place the Bootstrap JavaScript Bundle before the closing `</body>` tag:

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

---

## CSS ownership rules

Use `uab-theme.css` for:

* UAB color variables
* Bootstrap theme overrides
* Reusable UAB utility classes
* Reusable UI Kit components
* Shared focus, hover, validation, and interaction states
* Components documented in the UAB UI Kit

Use `site.css` for:

* Application-specific layouts
* Page-specific adjustments
* Styles that should not be shared by every UAB application

Do not place reusable UI Kit component styles in `site.css`.

When a new reusable component is required:

1. Confirm that Bootstrap cannot already provide the behavior.
2. Reuse existing UAB variables and utilities.
3. Add the smallest reusable component style to `uab-theme.css`.
4. Document the new component in the UAB UI Kit.
5. Do not use hard-coded colors when an existing UAB CSS variable is available.

---

## Bootstrap-first rules

* Use standard Bootstrap components before creating custom components.
* Do not recreate Bootstrap inputs, buttons, alerts, cards, modals, navbars, tabs, tables, or utilities.
* Apply UAB theme classes and documented UAB patterns to Bootstrap components.
* Do not create custom classes for spacing, layout, flexbox, grid, alignment, or responsiveness when Bootstrap utilities already exist.
* Do not wrap content in cards unless the requested layout or documented component specifically requires a card.
* Forms should not be automatically wrapped in cards.
* Use cards only when they represent a meaningful grouped container, summary panel, dashboard item, or documented card pattern.

---

## Forms

Use standard Bootstrap 5.3 form controls together with the UAB theme overrides.

Available themed form patterns include:

* Standard inputs and selects with UAB focus states
* Search input groups
* Checkboxes
* Radio buttons
* Switches
* Range controls
* Validation states
* Attachment upload

### Standard fields

Use Bootstrap classes:

* `form-label`
* `form-control`
* `form-select`
* `form-text`
* `input-group`
* `input-group-text`

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

### Search

Use an input group with a Bootstrap Icon and a UAB primary button:

```html
<form>
    <label for="txtSearch" class="form-label fw-semibold">Search</label>
    <div class="input-group">
        <span class="input-group-text">
            <i class="bi bi-search" aria-hidden="true"></i>
        </span>
        <input type="search" class="form-control" id="txtSearch" name="Search" placeholder="Search products or orders">
        <button type="submit" class="btn btn-primary uab-press">Search</button>
    </div>
</form>
```

### Selection controls

Use Bootstrap selection controls. The UAB theme provides green selected and focus states.

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

### Range controls

Use the standard Bootstrap `form-range` component. The UAB theme controls its selected color and focus state.

```html
<label for="rngPriority" class="form-label fw-semibold">Priority Level</label>
<input type="range" class="form-range" id="rngPriority" name="Priority" min="1" max="5" value="3">
```

### Attachment upload

Use the documented UAB attachment upload component when a styled file-upload experience is required.

Available classes include:

* `uab-file-upload`
* `uab-file-upload-input`
* `uab-file-upload-label`
* `uab-file-selection`

The component must:

* Preserve a native file input
* Support keyboard selection
* Include an associated label
* Display accepted file types and size limits
* Display the selected filename and size
* Provide an accessible remove button
* Use UAB variables and theme utilities
* Avoid inline colors and application-specific styling

Do not replace the native file input with an inaccessible clickable `<div>`.

### Validation

Use Bootstrap validation classes:

* `is-valid`
* `is-invalid`
* `valid-feedback`
* `invalid-feedback`

Associate feedback with the input using `aria-describedby`.

---

## HTML formatting

Follow the Bootstrap documentation formatting style.

* Keep HTML attributes on the same line unless the element becomes difficult to read.
* Do not add empty lines between every opening and closing tag.
* Use consistent indentation.
* Keep related elements together.
* Add spacing between logical component groups, not between every HTML element.

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

* Keep documentation-only wrappers separate from the reusable component code.
* Do not include the UI Kit documentation container in copied component code.
* A `code-card` may display code in the documentation, but it must not be included in the copied application markup.
* Include the component's functional wrapper, such as `<form>`, when it is required for a complete usable example.
* Each documented subsection should have its own focused code example.
* Do not return one excessively large example when smaller independent examples are more reusable.

---

## Optional DataTables integration

Use DataTables only for advanced administrative lists requiring search, ordering, pagination, or page-size controls.

DataTables is optional and is not required for standard responsive tables.

Use:

```html
<link rel="stylesheet" href="https://cdn.datatables.net/2.3.8/css/dataTables.bootstrap5.min.css">
```

```html
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="https://cdn.datatables.net/2.3.8/js/dataTables.min.js"></script>
<script src="https://cdn.datatables.net/2.3.8/js/dataTables.bootstrap5.min.js"></script>
```

Do not combine the `table-column-mobile` pattern with DataTables unless the documented integration explicitly supports it.

Disable ordering and searching for action columns.

---

## Updated code-generation process

Before writing code:

1. Inspect `uab-theme.css`, `site.css`, and the component documentation.
2. Determine whether the requested interface matches an existing UAB pattern.
3. If no UAB-specific pattern exists, use the standard Bootstrap 5.3 component.
4. Use Bootstrap utilities for layout and spacing.
5. Do not add a card wrapper unless it has a meaningful design purpose.
6. Add reusable custom CSS to `uab-theme.css` only when Bootstrap and existing UAB classes are insufficient.
7. Add application-specific CSS to `site.css`.
8. Explain why new CSS is required before creating it.
9. Preserve accessibility and responsive behavior.
10. Follow the documented compact HTML formatting style.

---

## Updated final validation checklist

Before returning code, verify:

* Bootstrap 5.3+ is used as the component foundation.
* Bootstrap JavaScript Bundle is included when interactive components require it.
* Bootstrap Icons are used correctly.
* UAB fonts are preserved.
* `uab-theme.css` is loaded after Bootstrap.
* `site.css` is loaded after `uab-theme.css`.
* Standard Bootstrap components were not unnecessarily recreated.
* No unauthorized colors were introduced.
* No alternative design system was introduced.
* Existing UAB component classes were reused.
* Forms were not unnecessarily wrapped in cards.
* Reusable styles were placed in `uab-theme.css`.
* Application-specific styles were placed in `site.css`.
* The layout is responsive.
* The markup is accessible.
* HTML follows the documented compact formatting style.
* Tables include synchronized `data-label` attributes when using the mobile table pattern.
* DataTables and the mobile table pattern were not combined without an approved integration.
* New CSS was avoided or minimized.
