# React — Common Errors & Quick Fixes

Short description
-----------------
Common problems when developing React apps and quick resolutions.

## 1. Module not found after pull

- Symptom: `Module not found` errors.
- Fix: `rm -rf node_modules && npm install` or `yarn install`.

## 2. Broken build after dependency update

- Symptom: build fails or runtime errors appear.
- Fix: pin versions in `package.json` and use lockfile; check breaking changes in changelogs.

## 3. Storybook not starting

- Symptom: Storybook crashes on startup.
- Fix: ensure compatible Storybook version and node version; clear caches.
