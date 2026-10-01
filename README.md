# @cubyt/style

Shared Cubyt brand foundations for colors, typography, radii, form controls, the logo mark, and Tailwind CSS v4.

## Package map

- `css/tokens.css`: brand and semantic design tokens, including light/dark themes.
- `css/forms.css`: opt-in form controls built on those tokens.
- `css/tailwind.css`: Tailwind CSS v4 token mappings.
- `css/brand.css`: logo mark styles.
- `assets/`: distributable brand assets.
- `CHANGELOG.md`: published changes.

## Install

```sh
npm install @cubyt/style
```

For a local Cubyt project, install the package from its repository path:

```sh
npm install ../branding/packages/style
```

## Use CSS variables

Import the tokens once in the application's global stylesheet:

```css
@import "@cubyt/style/tokens.css";

.panel {
  color: var(--ui-ink-strong);
  background: var(--ui-surface);
  border-color: var(--ui-border);
}
```

Overlay tokens used by `@cubyt/ui`, `@cubyt/modals` and `@cubyt/toasts` are also
included: `--ui-accent-soft`, `--ui-accent-border`, `--ui-danger*`,
`--ui-warning*`, `--ui-info*`, `--ui-field`, `--ui-field-border`, `--ui-scrim`,
`--ui-shadow-overlay` and `--brand-radius-xl`.

The palette switches between light and dark using `prefers-color-scheme`. Any
consumer can select a theme explicitly on the document root. Set `data-theme`
to `light`, `dark`, or `system`; omitting the attribute also follows the system
preference. This works for the shared tokens and the form controls below.

```html
<html data-theme="dark">
```

## Use shared form controls

Import the controls after the tokens. They are opt-in classes, so existing
forms keep their current appearance until migrated.

```css
@import "@cubyt/style/tokens.css";
@import "@cubyt/style/forms.css";
```

```html
<label class="cubyt-field">
  <span class="cubyt-label">Environment</span>
  <span class="cubyt-select-wrap">
    <select class="cubyt-select">
      <option>Production</option>
      <option>Staging</option>
    </select>
  </span>
</label>

<label class="cubyt-choice">
  <input type="checkbox" name="alerts" />
  Send error alerts
</label>
```

Available classes include `cubyt-field`, `cubyt-label`, `cubyt-hint`,
`cubyt-error`, `cubyt-input`, `cubyt-select`, `cubyt-select-wrap`,
`cubyt-textarea`, `cubyt-choice`, and `cubyt-switch`. Set
`aria-invalid="true"` on a field control to show its error border. Compose the
classes with application-specific layout classes as needed.

## Use the Cubyt logo

Import the brand stylesheet once, then compose the logo mark with your wordmark.
The mark color and dimensions are CSS variables, so this stays framework-agnostic:

```css
@import "@cubyt/style/brand.css";

.brand-mark {
  --cubyt-brand-size: 28px;
  --cubyt-brand-color: var(--ui-ink-strong);
}
```

```html
<span class="brand-mark cubyt-brand-mark" aria-label="Cubyt"></span>
```

The raw vector is also available as `@cubyt/style/assets/logo.svg`. Set
`--cubyt-brand-color` to any CSS color (or `currentColor`) and
`--cubyt-brand-size` to any valid CSS length.

## Use with Tailwind CSS v4

Import the Tailwind adapter after Tailwind itself:

```css
@import "tailwindcss";
@import "@cubyt/style/tailwind.css";
@import "@cubyt/style/tokens.css";
```

This exposes utilities such as `bg-canvas`, `bg-surface-soft`, `text-ink-strong`,
`border-border-default`, and the shared font and radius utilities.

## Publishing

This package is maintained at [CubytsAS/package-styles](https://github.com/CubytsAS/package-styles). See [CONTRIBUTING.md](./CONTRIBUTING.md) for repository conventions and its **Publish to npm** GitHub Actions workflow. The workflow calls the shared organization workflow in [`CubytsAS/.github`](https://github.com/CubytsAS/.github).

The organization must provide an Actions secret named `NPM_TOKEN` with publish access to the `@cubyt` npm scope. Do not commit npm credentials or place them in package files. Increment `version` in `package.json` before publishing; npm versions are immutable.
