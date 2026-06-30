# ACS / UAB UI Kit — Page Generation Prompt

Using the ACS / UAB UI Kit instructions, the existing `uab-theme.css`, `site.css`, and the component documentation, generate the following page or interface:

[Describe the page, view, or component here.]

Example:

Create a Home page with a hero section, alert message, sample request form, responsive table, status badges, and a final callout section.

---

## Context

Use the existing application layout and styling.

Do not change the main layout unless I explicitly ask.
Do not change controllers, routes, authentication, authorization, database code, or business logic.
Do not remove existing scripts or dependencies.
Do not add duplicate Bootstrap references.
Do not modify the ACS / UAB UI Kit template folder.

This is a UI generation task only.

---

## Required references

Before generating the page, review:

* `.github/copilot-instructions.md`
* `acs-ui-kit-template/docs/instructions.md`
* `acs-ui-kit-template/docs/acs-ui-kit.html`
* `acs-ui-kit-template/css/uab-theme.css`
* The application’s current `site.css`
* The existing layout and shared partials
* Any existing views with similar patterns

---

## Requirements

* Use existing ACS / UAB UI Kit patterns first.
* Use standard Bootstrap components when no ACS / UAB-specific pattern exists.
* Reuse existing Bootstrap and ACS / UAB classes.
* Use Bootstrap utilities for layout, spacing, flexbox, grid, and responsiveness.
* Use Bootstrap Icons when icons are helpful.
* Do not invent colors.
* Do not invent CSS classes unnecessarily.
* Do not create new CSS unless absolutely necessary.
* Do not wrap content in cards unless the design requires it.
* Use cards only for meaningful grouped content, dashboard items, summary panels, or documented card patterns.
* Keep reusable CSS in `uab-theme.css`.
* Keep page-specific CSS in `site.css`.
* Prefer no new CSS for simple layout work.
* Make the interface responsive and accessible.
* Use semantic HTML and proper heading order.
* Use labels for form fields.
* Use `aria-describedby` for helper text or validation messages when appropriate.
* Use `aria-hidden="true"` for decorative icons.
* Follow the existing compact HTML/Razor formatting style.
* Include JavaScript only when required.
* Preserve existing JavaScript hooks, IDs, names, validation attributes, and form behavior.

---

## Forms

If the page includes a form:

* Use Bootstrap form classes.
* Use ACS / UAB theme styles already defined in `uab-theme.css`.
* Preserve model binding if this is an existing form.
* Preserve input `name` attributes.
* Preserve input `id` attributes.
* Preserve hidden fields.
* Preserve validation summaries.
* Preserve anti-forgery tokens.
* Do not replace working form logic with sample markup.

Use classes such as:

* `form-label`
* `form-control`
* `form-select`
* `form-text`
* `input-group`
* `input-group-text`
* `form-check`
* `form-check-input`
* `form-check-label`
* `btn`
* `btn-primary`
* `btn-outline-primary`

---

## Tables

If the page includes a table:

* Use Bootstrap responsive table patterns.
* Preserve existing DataTables behavior if DataTables is already used.
* Do not add DataTables unless the table needs search, sort, pagination, or page-size controls.
* Do not combine DataTables with mobile table patterns unless the UI Kit explicitly supports that integration.
* If using the mobile table pattern, keep `data-label` values synchronized with table headers.

---

## Before implementation

Before making file changes, give me a short plan.

The plan must include:

* Which file or view you will update.
* Which ACS / UAB UI Kit patterns you will use.
* Which Bootstrap components you will use.
* Whether any CSS changes are needed.
* Whether any JavaScript is needed.
* Any risks or assumptions.

Do not modify files until I approve the plan.

---

## After approval

After I approve the plan:

* Implement only the approved UI changes.
* Modify only the necessary view files.
* Avoid unnecessary CSS changes.
* Do not modify unrelated files.
* Build the solution if appropriate.
* Fix only errors caused by this UI update.

---

## Final response

After implementation, provide:

* A summary of files changed.
* A short explanation of the page sections created.
* A list of Bootstrap components reused.
* A list of ACS / UAB UI Kit classes or patterns reused.
* Any CSS or JavaScript added, if applicable.
