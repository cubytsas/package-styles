# @cubyt/style

Shared Cubyt brand foundations for colors, typography, radii, the logo mark, and Tailwind CSS v4.

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

The palette switches between light and dark using `prefers-color-scheme`. Any
consumer can override that behavior by setting the token variables on its own
theme root after importing the package.

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

This package is maintained at [CubytsAS/package-styles](https://github.com/CubytsAS/package-styles). Use its **Publish to npm** GitHub Actions workflow to publish after validating the package contents. The workflow calls the shared organization workflow in [`CubytsAS/.github`](https://github.com/CubytsAS/.github).

The organization must provide an Actions secret named `NPM_TOKEN` with publish access to the `@cubyt` npm scope. Do not commit npm credentials or place them in package files. Increment `version` in `package.json` before publishing; npm versions are immutable.
