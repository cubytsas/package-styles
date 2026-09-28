# Changelog

All notable changes to `@cubyt/style` are documented here.

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
