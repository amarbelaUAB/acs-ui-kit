# ACS / UAB UI Kit Template Integration Prompt

You are working on an ASP.NET MVC or ASP.NET Core MVC application.

Your task is to apply the ACS / UAB UI Kit template and styling to this application.

This is a style/template integration task only.

Do not rewrite the application architecture.
Do not remove existing functionality.
Do not remove existing dependencies.
Do not modernize unrelated code.
Do not refactor unrelated files.
Do not remove jQuery, jQuery Validation, Unobtrusive Validation, DataTables, Bootstrap scripts, or any existing application-specific JavaScript unless I explicitly approve it.

---

## Source of truth

The ACS / UAB UI Kit resources folder is located at:

`./acs-ui-kit-template`

This folder is outside the solution and contains the reusable UI Kit resources, including:

* `docs`
* `css`
* `images`
* Markdown instruction files
* The UI Kit component library index file
* Theme CSS files
* Brand assets

Use this folder as the single source of truth for:

* Layout patterns
* Navbar
* Footer
* Typography
* Colors
* Buttons
* Forms
* Tables
* Alerts
* Cards
* Badges
* Spacing
* Responsive behavior
* Accessibility patterns
* Brand assets

Read from this folder, but do not modify the files inside this folder.

If assets are required, copy only the required files into the application’s normal public asset folder, such as:

* `wwwroot/images` for ASP.NET Core MVC
* `Content/images`, `Images`, or the existing image folder for ASP.NET MVC 5 / .NET Framework

Do not create placeholder logos.
Do not create fake brand assets.
Do not invent new branding.
Use only the assets from the UI Kit resource folder or assets already present in the application.

---

## Required planning step

Before making any file changes, inspect the project and the UI Kit resources, then create an implementation plan.

Do not modify files yet.

The plan must include:

1. Which project type you detected:

   * ASP.NET Core MVC
   * ASP.NET MVC 5 / .NET Framework

2. Which UI Kit files you reviewed, including:

   * UI Kit index/component library
   * Markdown instruction files
   * Theme CSS files
   * Image/assets folder

3. Which Bootstrap version and setup the application currently uses:

   * Local Bootstrap files
   * CDN Bootstrap references
   * Bundled Bootstrap references
   * Existing Bootstrap JavaScript Bundle
   * Existing jQuery-based Bootstrap setup, if applicable

4. Whether Bootstrap needs to be updated to align with the UI Kit.

5. Which application files you plan to modify.

6. Which files you plan to create, if any.

7. Which assets you plan to copy into the application, if any.

8. Which CSS files and script references you plan to add or update.

9. Which existing dependencies you will preserve, especially:

   * jQuery
   * jQuery Validation
   * Unobtrusive Validation
   * DataTables
   * Bootstrap scripts
   * App-specific JavaScript

10. Any risks, assumptions, or areas that need special care.

Wait for my approval before implementing.

After I approve the plan, make only the changes described in the approved plan.

---

## Main goal

Update the application so it visually aligns with the ACS / UAB UI Kit.

The application should keep its existing behavior and functionality, but the layout and UI should match the ACS / UAB design language.

This includes:

* Main layout
* Navbar
* Footer
* Page containers
* Buttons
* Forms
* Tables
* Alerts
* Cards
* Badges
* Spacing
* Typography
* Font usage
* Responsive layout
* Accessibility improvements related to markup and styling

---

## UI Kit priority order

Use this priority order when creating or updating UI:

1. Existing ACS / UAB UI Kit component or documented pattern
2. Standard Bootstrap 5.3 component
3. Bootstrap utility classes
4. Minimal reusable custom CSS only when the first three options are insufficient

Do not recreate standard Bootstrap components with custom HTML or CSS.

Do not recreate Bootstrap inputs, buttons, alerts, cards, modals, navbars, tabs, tables, or utilities.

Use Bootstrap components and utilities first.

---

## Bootstrap dependency rule

ASP.NET MVC and ASP.NET Core MVC templates may already include Bootstrap.

Before adding Bootstrap references, inspect the existing layout, bundle configuration, and static files.

If Bootstrap is already present:

* Preserve the existing Bootstrap setup when possible.
* Do not add duplicate Bootstrap CSS references.
* Do not add duplicate Bootstrap JavaScript references.
* Do not remove Bootstrap unless explicitly approved.
* Do not add a CDN reference if the app already uses local Bootstrap files, unless this is approved in the plan.
* Do not add local Bootstrap files if the app already uses CDN references, unless this is approved in the plan.
* If the UI Kit requires Bootstrap 5.3 and the app uses an older Bootstrap version, explain the required update in the plan before changing it.
* Prefer updating the existing Bootstrap reference instead of adding a second one.
* Avoid mixing Bootstrap versions.

If Bootstrap is not present:

* Add Bootstrap 5.3 or later using the project’s existing asset approach.
* Use CDN only if that matches the project’s current pattern.
* Use local files only if that matches the project’s current pattern.
* Explain the chosen approach in the plan before implementing.

For ASP.NET MVC 5 / .NET Framework applications, be extra careful with older Bootstrap versions because upgrading from Bootstrap 3 or 4 to Bootstrap 5 can affect markup, scripts, and layout behavior.

Do not upgrade Bootstrap blindly.

---

## Required technology

Use only the existing application technology plus the UI Kit resources.

The UI Kit is based on:

* Bootstrap 5.3 or later
* Bootstrap JavaScript Bundle
* Bootstrap Icons
* UAB Adobe Fonts
* `uab-theme.css`
* Existing application stylesheet: `site.css`

Preserve existing application dependencies.

Do not add unnecessary packages.

Do not convert the app to a different framework version.

Do not upgrade the application unless I explicitly ask.

---

## Stylesheet order rule

The final stylesheet order should preserve existing app behavior while allowing the ACS / UAB theme to apply correctly.

When Bootstrap 5.3 is used, the preferred order is:

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

If the application already has working CSS bundles, preserve the bundle system unless a small update is required.

Do not break existing CSS references.

Do not add duplicate Bootstrap references.

---

## Required script behavior

Place the Bootstrap JavaScript Bundle before the closing `</body>` tag when required by the UI Kit or Bootstrap interactive components.

Preserve existing scripts unless there is a clear and approved reason to change them.

Do not remove:

* jQuery
* jQuery Validation
* Unobtrusive Validation
* DataTables
* Existing app-specific scripts

Avoid duplicate or conflicting Bootstrap script references where possible, but do not remove anything without explaining it in the plan first.

If the project uses Bootstrap 5, prefer the Bootstrap JavaScript Bundle.

If the project uses an older Bootstrap version, do not replace the script setup without explaining the risk in the plan and receiving approval.

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

1. Confirm that Bootstrap cannot already provide the behavior.
2. Confirm that the UI Kit does not already provide the pattern.
3. Reuse existing UAB variables and utilities.
4. Add the smallest possible CSS.
5. Use `uab-theme.css` only for reusable UI Kit styles.
6. Use `site.css` only for application-specific styles.
7. Explain why the new CSS is required before creating it.
8. Do not use hard-coded colors when an existing UAB CSS variable is available.

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

Do not wrap content in cards unless the requested layout or documented component specifically requires a card.

Forms should not automatically be wrapped in cards.

Use cards only when they represent a meaningful grouped container, summary panel, dashboard item, or documented card pattern.

---

## Layout requirements

Update the main layout so the application uses the ACS / UAB look and feel.

The layout should include, when appropriate:

* UAB/ACS styled navbar
* UAB/ACS styled footer
* Proper page container width
* Consistent spacing
* Correct font loading
* Correct CSS order
* Bootstrap Icons if already used or required
* Responsive behavior
* Accessible navigation markup
* Skip link if appropriate
* Main content landmark if appropriate

Use partial views for reusable layout elements when appropriate, such as:

* `_Navbar.cshtml`
* `_Footer.cshtml`

Do not create unnecessary partials if the existing project structure is simpler and does not need them.


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

## ASP.NET Core MVC guidance

For ASP.NET Core MVC applications, review and update only what is needed, usually:

* `Views/Shared/_Layout.cshtml`
* `Views/Shared/_Navbar.cshtml`, if it exists or should be created
* `Views/Shared/_Footer.cshtml`, if it exists or should be created
* `wwwroot/css/uab-theme.css`
* `wwwroot/css/site.css`
* `wwwroot/images`
* Existing Razor views only when needed for visual consistency

Preserve:

* Existing controllers
* Existing models
* Existing view models
* Existing routes
* Existing authentication
* Existing authorization
* Existing validation
* Existing scripts
* Existing NuGet packages

Do not change `Program.cs` unless there is a clear, approved reason.

---

## ASP.NET MVC 5 / .NET Framework guidance

For ASP.NET MVC 5 / .NET Framework applications, review and update only what is needed, usually:

* `Views/Shared/_Layout.cshtml`
* Existing shared partial views
* `Content/site.css`
* Existing theme CSS files
* Existing image folders
* `App_Start/BundleConfig.cs` only if CSS or script references need to be added using the existing bundle system

Preserve:

* jQuery
* jQuery Validation
* Unobtrusive Validation
* Bootstrap scripts
* DataTables
* Existing bundles
* Existing controllers
* Existing models
* Existing routes
* Existing authentication
* Existing authorization
* Existing business logic

Do not convert the application to ASP.NET Core.

Do not upgrade framework versions.

Do not replace the existing bundle system unless I explicitly approve it.

---

## View update rules

When updating existing views:

* Keep existing form actions.
* Keep existing routes.
* Keep existing model bindings.
* Keep existing validation attributes.
* Keep existing input `name` attributes.
* Keep existing input `id` attributes unless a change is required and approved.
* Keep existing hidden fields.
* Keep existing validation summaries.
* Keep existing anti-forgery tokens.
* Keep existing controller/action names.
* Keep existing business logic.
* Keep existing JavaScript hooks, IDs, and classes used by scripts.

Update markup only as needed for UI consistency.

Prefer Bootstrap and UI Kit classes over custom CSS.

Do not replace working forms with unrelated demo markup.

Do not remove functional HTML just because it is not part of the UI Kit demo.

---

## Forms guidance

Use standard Bootstrap form controls together with UAB theme overrides.

Use Bootstrap classes such as:

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

For validation, use Bootstrap validation classes when compatible with the current Bootstrap version:

* `is-valid`
* `is-invalid`
* `valid-feedback`
* `invalid-feedback`

Associate feedback with the input using `aria-describedby` when appropriate.

Do not remove existing server-side validation helpers.

Do not remove ASP.NET MVC validation summaries.

Do not remove unobtrusive validation attributes.

---

## Attachment upload guidance

Use the documented ACS / UAB attachment upload component when a styled file-upload experience is required.

Available classes may include:

* `uab-file-upload`
* `uab-file-upload-input`
* `uab-file-upload-label`
* `uab-file-selection`

The component must:

* Preserve a native file input.
* Support keyboard selection.
* Include an associated label.
* Display accepted file types and size limits.
* Display the selected filename and size when JavaScript is available.
* Provide an accessible remove button when needed.
* Use UAB variables and theme utilities.
* Avoid inline colors.
* Avoid application-specific styling in reusable component CSS.

Do not replace the native file input with an inaccessible clickable `<div>`.

---

## Tables guidance

Use standard Bootstrap responsive tables unless the UI Kit documents a more specific pattern.

Use DataTables only for advanced administrative lists requiring:

* Search
* Ordering
* Pagination
* Page-size controls

DataTables is optional and is not required for standard responsive tables.

If DataTables is already used in the application, preserve it.

When using DataTables:

* Use the Bootstrap-compatible DataTables styling that matches the Bootstrap version in the project.
* Disable ordering and searching for action columns.
* Preserve existing DataTables initialization logic unless an approved update is required.
* Do not combine the `table-column-mobile` pattern with DataTables unless the documented integration explicitly supports it.

If using the mobile table pattern, ensure `data-label` attributes stay synchronized with table headers.

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

---

## Accessibility rules

Preserve or improve accessibility.

Use:

* Semantic HTML
* Proper labels for form fields
* Associated labels using `for` and `id`
* `aria-describedby` for helper text and validation messages when appropriate
* Accessible button text
* `aria-hidden="true"` for decorative icons
* Keyboard-accessible controls
* Responsive layouts that do not depend only on color or hover

Do not remove accessibility attributes from existing markup.

Do not create inaccessible custom controls when a native control or Bootstrap component is available.

---

## Multiple views guidance

If I ask you to create multiple views, follow the same UI Kit rules.

Before implementing, give me a plan and wait for approval.

The plan must include:

* Views to create or update
* Controller actions needed, if any
* View models needed, if any
* UI Kit components to use
* Files to modify or create
* Any sample data or placeholder content needed

When creating views:

* Use the existing application layout.
* Use ACS / UAB UI Kit patterns.
* Use Bootstrap grid, cards, tables, forms, buttons, alerts, badges, and utilities.
* Use placeholder sample data only if no model exists yet.
* Do not create database logic unless I explicitly ask.
* Do not create services unless I explicitly ask.
* Do not change authentication.
* Do not remove existing scripts or dependencies.
* Keep controllers thin.
* Use strongly typed view models when appropriate.
* Avoid unnecessary custom CSS.

---

## What not to do

Do not:

* Remove jQuery.
* Remove jQuery Validation.
* Remove Unobtrusive Validation.
* Remove DataTables.
* Remove Bootstrap scripts.
* Remove existing app-specific JavaScript.
* Add duplicate Bootstrap CSS references.
* Add duplicate Bootstrap JavaScript references.
* Mix Bootstrap versions.
* Change controller logic unless explicitly approved.
* Change database code.
* Change authentication logic.
* Change authorization logic.
* Change route configuration unless required for static assets and approved.
* Delete existing views.
* Delete existing CSS without confirming it is obsolete or duplicated.
* Add unnecessary packages.
* Convert the app to a different framework version.
* Create fake demo pages unless I explicitly ask.
* Replace existing working functionality with sample UI Kit markup.
* Add broad refactors outside the styling/template task.
* Introduce a different design system.
* Introduce unauthorized colors.
* Use inline styles unless there is a very small, justified exception.

---

## Implementation process

Follow this process:

1. Inspect the ACS / UAB UI Kit resources folder.
2. Review the UI Kit index/component library file.
3. Review all Markdown instruction files.
4. Review the theme CSS and available image assets.
5. Inspect the MVC application structure.
6. Determine whether the app is ASP.NET Core MVC or ASP.NET MVC 5 / .NET Framework.
7. Detect the existing Bootstrap version and setup.
8. Detect existing script dependencies.
9. Create an implementation plan.
10. Wait for my approval before modifying files.
11. After approval, update the main layout.
12. Add or update shared navbar/footer partials if appropriate.
13. Add or update CSS references only as needed.
14. Add or update script references only if needed.
15. Copy only required assets into the application’s normal asset folders.
16. Update basic view markup only where needed for visual consistency.
17. Preserve all existing dependencies and scripts.
18. Build the solution.
19. Fix only errors caused by the implementation.
20. Provide a final summary of changed files and what was changed.

---

## Final validation checklist

Before finishing, verify:

* The existing Bootstrap setup was detected before changes were made.
* Duplicate Bootstrap references were not introduced.
* Bootstrap versions were not mixed.
* Bootstrap 5.3+ is used as the component foundation when the project supports it.
* Bootstrap JavaScript Bundle is included when interactive Bootstrap 5 components require it.
* Bootstrap Icons are used correctly.
* UAB fonts are preserved.
* `uab-theme.css` is loaded after Bootstrap.
* `site.css` is loaded after `uab-theme.css`.
* Existing scripts and dependencies were preserved.
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
* Existing controller logic was preserved.
* Existing form behavior was preserved.
* Existing validation behavior was preserved.
* Existing authentication and authorization were preserved.
* The solution builds successfully.
* Only implementation-related errors were fixed.

---

## Expected result

The final application should:

* Keep its existing functionality.
* Keep its existing dependencies.
* Keep its existing JavaScript behavior.
* Keep its existing routes and controller logic.
* Visually align with the ACS / UAB UI Kit.
* Use the same design language as the UI Kit component library.
* Be responsive.
* Be accessible.
* Avoid unnecessary custom CSS.
* Avoid unnecessary code changes.
* Avoid duplicate framework or library references.

The result should look like it belongs to the same family as the ACS / UAB UI Kit while keeping the application’s original behavior intact.
