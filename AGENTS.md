# FlightFind

Design assets for a **FlightFind** flight-comparison app (target platform: React Native / iOS style). This repo currently holds static HTML design mockups, design tokens, and a spec — there is no build system, package manager, dependencies, tests, or linters.

- `01-intake-home.html` — pre-search intake page + home
- `02-search-fields.html` — search fields (quick search / hidden-city / reverse-ticket modes)
- `03-results.html` — results pages for the three modes
- `04-detail-my.html` — flight detail page + "My" page
- `design-tokens.json` — colors (light/dark), typography, spacing, radius; intended for future React Native use
- `flightfind_spec.md` — the product/design spec (source of truth for requirements)
- `logo.svg` — wordmark logo

`flightfind_spec.md` references a `mockups/` folder, but the mockup HTML files currently live at the repo root (a stray empty `mockups` file also exists).

## Cursor Cloud specific instructions

### Running
These are standalone static HTML files — serve the repo root over HTTP and open each page (e.g. `http://localhost:8000/01-intake-home.html`). Plain `python3 -m http.server 8000` works: all four mockups declare `<!DOCTYPE html>` and `<meta charset="UTF-8">`, so text renders correctly.

### Lint / Test / Build
None configured. There is nothing to install, lint, test, or build. `design-tokens.json` and `flightfind_spec.md` guide future React Native implementation.
