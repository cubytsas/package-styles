# @cubyt/style

Shared styles for Cubyt Sas products: design tokens, light and dark themes, form controls, Tailwind CSS v4 mappings, and the Cubyt mark.

## Install

```sh
npm install @cubyt/style
```

## CSS tokens and themes

Import the tokens once in your global stylesheet:

```css
@import "@cubyt/style/tokens.css";

.card {
  color: var(--ui-ink);
  background: var(--ui-surface);
  border: 1px solid var(--ui-border);
}
```

The default theme follows the operating system. To choose one explicitly, set `data-theme` on `<html>`:

```html
<html data-theme="dark">
```

Supported values are `light`, `dark`, and `system`.

## Form controls

Import `forms.css` after the tokens. Its classes are opt-in, so they only affect elements where you use them.

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
```

Available classes: `cubyt-field`, `cubyt-label`, `cubyt-hint`, `cubyt-error`, `cubyt-input`, `cubyt-select`, `cubyt-select-wrap`, `cubyt-textarea`, `cubyt-choice`, and `cubyt-switch`. Set `aria-invalid="true"` on a field control to show its error state.

## Tailwind CSS v4

Import the adapter after Tailwind and the tokens:

```css
@import "tailwindcss";
@import "@cubyt/style/tokens.css";
@import "@cubyt/style/tailwind.css";
```

It maps the shared colors, fonts, and radii to Tailwind utilities such as `bg-surface`, `text-ink`, and `rounded-md`.

## Cubyt mark

Import `brand.css` and use the mark alongside your wordmark:

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
