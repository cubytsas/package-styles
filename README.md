# @cubyt/style

Official Cubyt design foundation for every product: light and dark palettes, type and spacing scales, gradients, interaction states, elevation, form controls, Tailwind CSS v4 mappings, and brand assets.

## Install

```sh
npm install @cubyt/style
```

## CSS entry points

Import Tailwind's adapter and tokens once in the app's global stylesheet. `base.css` is optional and applies the shared page defaults, font rendering, focus ring, selection color, and reduced-motion behavior.

```css
@import "tailwindcss";
@import "@cubyt/style/tailwind.css";
@import "@cubyt/style/tokens.css";
@import "@cubyt/style/base.css";
@import "@cubyt/style/forms.css";
@import "@cubyt/style/brand.css";
```

Use `tokens.css` without Tailwind by itself, or import `forms.css` only where the opt-in `.cubyt-*` form classes are used. Component styles are maintained in `@cubyt/ui`, `@cubyt/modals`, and `@cubyt/toasts` and should be imported after the tokens.

## Themes

The default follows the operating system. Set `data-theme` on `<html>` to override it:

```html
<html data-theme="dark">
```

Supported values are `light`, `dark`, and `system`. Components inherit the same semantic variables; keep theme-specific values in `tokens.css` rather than adding per-component dark overrides.

## Design tokens

Use semantic variables in CSS and their matching Tailwind classes in components:

| Foundation | CSS variable | Tailwind example |
| --- | --- | --- |
| Page and panels | `--ui-canvas`, `--ui-surface`, `--ui-surface-soft`, `--ui-surface-raised` | `bg-canvas`, `bg-surface`, `bg-surface-soft` |
| Text and borders | `--ui-ink`, `--ui-ink-strong`, `--ui-muted`, `--ui-border` | `text-ink`, `text-muted`, `border-border-default` |
| Hover and selection | `--ui-hover`, `--ui-selected`, `--ui-selected-ink` | `hover:bg-hover`, `bg-selected`, `text-selected-ink` |
| Actions and status | `--ui-action`, `--ui-accent`, `--ui-danger`, `--ui-warning`, `--ui-info` | `bg-action`, `bg-accent`, `text-danger` |
| Shape, type, and elevation | `--brand-radius-*`, `--brand-text-*`, `--ui-shadow-*` | `rounded-md`, `text-sm`, `shadow-overlay` |
| Brand treatment | `--brand-gradient`, `--brand-gradient-soft` | `bg-brand-gradient`, `bg-brand-gradient-soft` |

The spacing scale uses a 4px base, so numeric Tailwind utilities such as `gap-2`, `p-4`, and `mt-6` follow the same Cubyt rhythm. Font, type-size, line-height, tracking, radii, focus, and motion tokens are exposed through `tailwind.css`.

Brand gradient helpers are available as `brand-rule`, `brand-outline`, and `brand-text`. They respect `prefers-reduced-motion` and can be combined with regular layout and radius utilities.

## Form controls

```html
<label class="cubyt-field">
  <span class="cubyt-label">Environment</span>
  <input class="cubyt-input" placeholder="Production" />
  <span class="cubyt-hint">Choose where the change applies.</span>
</label>
```

Available classes: `cubyt-field`, `cubyt-label`, `cubyt-hint`, `cubyt-error`, `cubyt-input`, `cubyt-select`, `cubyt-select-wrap`, `cubyt-textarea`, `cubyt-choice`, and `cubyt-switch`. Set `aria-invalid="true"` on a control to show validation styling. For a fully custom option menu, use `DropdownSelect` from `@cubyt/ui/react`; native select popups are controlled by the browser or operating system.

## Brand mark

```css
@import "@cubyt/style/brand.css";

.brand-mark {
  --cubyt-brand-size: 28px;
  --cubyt-brand-color: var(--ui-ink-strong);
}
```

```html
<span class="cubyt-brand-mark brand-mark" aria-label="Cubyt"></span>
```

## Components

For shared buttons, custom selects, popovers, notices, and primitives, use `@cubyt/ui`. Use `@cubyt/modals` for dialogs, drawers, and sheets, and `@cubyt/toasts` for notifications. Their CSS is token-based and follows the same theme, spacing, typography, and motion system.
