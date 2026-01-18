# Repository Guidelines

## Project Structure & Module Organization
This repo is a single-file PWA with a few static assets:
- `index.html` contains all HTML, CSS, and JavaScript.
- `manifest.json` defines the PWA metadata and icons/screenshots.
- `sw.js` provides offline caching.
- `icon-*.png` and `screenshot-*.png` are PWA assets.
- `README.md` and `GEMINI.md` provide project context.

## Build, Test, and Development Commands
There is no build step or bundler. Use a static server for local testing:
- `python3 -m http.server 8080` serves the repo at `http://localhost:8080/`.
  This is required to test the service worker and PWA install flow.

## Coding Style & Naming Conventions
- Indentation: 4 spaces in HTML/CSS/JS.
- JavaScript: `camelCase` for functions and variables (`updateFromXP`), `UPPER_SNAKE_CASE` for constants (`XP_PER_MIN`).
- Keep logic in small, single-purpose functions and avoid external dependencies.
- Prefer direct DOM access via `document.getElementById` for this small app.

## Testing Guidelines
No automated tests are configured. Manual checks are expected:
- Verify each input updates the other two values.
- Test edge cases like empty input and decimals.
- Confirm offline behavior in Chrome DevTools → Application tab.

## Commit & Pull Request Guidelines
Recent commits use short, imperative messages (e.g., “Add README.md…”). Follow that style.
For changes:
- Describe the user-facing impact in the PR description.
- Include a screenshot when modifying UI or PWA assets.
- Mention any manual testing performed (e.g., “Checked PWA install and offline caching”).

## PWA Notes
Service worker caching is versioned in `sw.js`. If you change cached assets, bump
`CACHE_NAME` so updates are picked up. Keep `manifest.json` icons and screenshots
in sync with actual files.
