# Changelog

All notable changes to `@cubyt/style` are documented here.

## [1.2.0] - 2026-10-09

### Added

- Official spacing, type scale, line-height, tracking, motion, elevation, focus, selection, hover, tooltip, and semantic surface tokens.
- Shared Cubyt mint-to-blue-to-lilac gradients and reusable Tailwind utilities for gradient rules, outlines, text, and soft surfaces.
- An optional app-wide `base.css` foundation for type rendering, page defaults, selection, focus, and reduced motion.
- Tailwind mappings for the full design foundation, including typography, semantic interaction states, and elevation.

### Changed

- Refined light and dark palettes to match the current Cubyt product UI and use consistent active and hover states across themes.
- Reorganized form styles around shared spacing, radius, focus, and field tokens.
- Fixed the brand mark mask path so the published stylesheet finds its logo asset.

## [1.1.0] - 2026-10-01

### Added

- Explicit `data-theme="light|dark|system"` selection, while preserving the existing system-preference default.
- Opt-in form styles for fields, inputs, selects, textareas, checkbox/radio choices, switches, hints, validation errors, focus, and disabled states.
- `forms.css` package export and usage documentation.

## [1.0.1] - 2026-09-28

### Added

- Accent-soft, danger, warning, info, form field, scrim, and overlay shadow tokens for overlays such as `@cubyt/modals` and `@cubyt/toasts`, with light and dark values.
- `--brand-radius-xl` radius token.
- Tailwind CSS v4 mappings for the new tokens (`bg-danger`, `bg-accent-soft`, `border-info-border`, `shadow-overlay`, `rounded-xl`, and more).

### Changed

- Publish from GitHub Actions with npm provenance attestations linking the package to its source commit and workflow.

## [1.0.0] - 2026-09-27

Initial public release.

### Added

- Shared CSS custom properties for Cubyt brand typography, radii, UI surfaces, text, borders, actions, and status colors.
- Light and dark color schemes, with dark tokens selected through `prefers-color-scheme`.
- Tailwind CSS v4 theme mappings for the shared brand tokens.
- Framework-agnostic Cubyt logo mark styles and the SVG logo asset.
- Explicit package exports and a minimal npm file allowlist.
- MIT license.
