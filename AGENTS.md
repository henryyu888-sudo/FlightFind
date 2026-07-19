# FlightFind

Static HTML prototypes. No build system, package manager, dependencies, tests, or linters.

- `main.html` — "FlightFind" mobile flight-search app prototype (Traditional Chinese UI). Self-contained: inline `<style>` + `<script>`, with mock flight data embedded in the script. Core flow: pick a route → search → view results/detail.
- `japan-trip-2026.html` — a standalone travel-itinerary page.

## Cursor Cloud specific instructions

### Running
These are plain static files; serve the repo root over HTTP and open the pages in a browser (e.g. `http://localhost:8000/main.html`).

Non-obvious caveat: `main.html` has no `<meta charset>` and no `<!DOCTYPE>`, so its Traditional Chinese text renders as mojibake unless the server sends `Content-Type: text/html; charset=utf-8`. Plain `python3 -m http.server` does NOT send a charset and produces garbled text. Serve with an explicit UTF-8 charset instead:

```
python3 -c "import http.server,socketserver; h=http.server.SimpleHTTPRequestHandler; h.extensions_map={**h.extensions_map, '.html':'text/html; charset=utf-8', '.htm':'text/html; charset=utf-8'}; socketserver.TCPServer(('',8000),h).serve_forever()"
```

(`japan-trip-2026.html` declares its own `<meta charset="UTF-8">` and renders correctly under any server, but using the command above keeps both pages correct.)

### Lint / Test / Build
None configured. There is nothing to install, lint, test, or build.
