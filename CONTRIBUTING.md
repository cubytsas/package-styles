# Contributing

## Repository layout

- `css/` contains the published stylesheets. Keep each stylesheet focused on one concern.
- `assets/` contains static brand assets distributed with the package.
- `README.md` is the consumer guide; `CHANGELOG.md` records release changes.
- `package.json` is the source of truth for exports, published files, and package version.
- `.github/workflows/` contains the npm publishing workflow.

## CSS conventions

- Keep existing public import paths stable. Map them to internal files through `package.json` `exports`.
- Add opt-in component classes instead of styling every native element globally.
- Build component colors, surfaces, borders, and radii from the shared CSS variables in `tokens.css`.
- Keep theme-specific values in the token layer so components inherit light, dark, or system themes automatically.
- Include keyboard focus, disabled, invalid, and reduced-motion states where they apply.

## Release checklist

1. Update `CHANGELOG.md` and increment the package version in `package.json`.
2. Check the manifest JSON and inspect the npm package contents with `npm pack --dry-run`.
3. Publish through the repository's **Publish to npm** GitHub Actions workflow. The workflow is triggered by a `v*` tag or manually.

Do not commit npm tokens or other publish credentials.
