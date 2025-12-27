<!-- Copilot / AI Agent guidance for contributors and AI copilots -->
# MyHamDashboard — Copilot Instructions

Summary
- Purpose: Single-file local dashboard for weather, radar, and propagation info. Primary files: `Dashboard.html` (UI + logic), `server.py` (optional CORS/proxy server), `README.MD` (usage).

What to edit
- `Dashboard.html`: contains all runtime JS. Key anchors:
  - `API_KEY` constant near the top — must be set for Gemini features.
  - `contentData` array (around the "DEFINE CONTENT URLs AND TITLES" section) — edit tiles here.
  - `IMAGE_REFRESH_RATE_MS` controls automatic reload frequency.
  - `LATITUDE` / `LONGITUDE` for the weather ticker.
  - `WEATHER_API_URL` and `updateTicker()` implement the ticker; use `open-meteo` pattern present in the file.

Run & debug
- No build system. Two recommended ways to run locally:
  1. Quick: `python -m http.server` from the project folder.
  2. Preferred for CORS/proxy: `python server.py` which starts `CORSRequestHandler` and exposes `/proxy?url=<encoded-url>`.
     - `server.py` shows how to call the proxy: `/proxy?url=https%3A%2F%2Fexample.com` (it forwards headers and retries).
  - To change port: set `PORT` env var before running `server.py` (e.g., Windows PowerShell: `setx PORT 8080` or `powershell -Command $env:PORT=8080; python server.py`).

Security & secrets
- `Dashboard.html` contains a plain `API_KEY` variable. Never commit real keys. Prefer setting it locally before running.
- The Gemini request in the file uses a model-specific URL and `tools: [{ "google_search": {} }]` in the payload. Ensure the key has Google Search Grounding enabled if you need live grounding.

Patterns & conventions
- Single-file UI: Most logic is in `Dashboard.html` — treat it as the source of truth for UI behavior.
- Remote-first content: tiles are remote images; many will fail due to CORS — use `server.py`'s `/proxy` for unstable sources.
- Cache-busting: images use a `t=` query param and `IMAGE_REFRESH_RATE_MS` for periodic refreshes — update carefully.
- Lightbox behavior: `openLightbox(url, type)` shows images/videos; `getContentType()` chooses type heuristically.

Integration points
- Gemini API: `API_URL` is constructed with `API_KEY` and points to a model endpoint. The `callGeminiPropagationAnalysis()` function posts JSON and expects `data.candidates[0].content.parts[0].text`.
- Weather/ticker: uses `open-meteo` JSON schema (see `WEATHER_API_URL`) and maps `weather_code` via `WMO_CODES` in the file.
- Proxy: `server.py` implements robust fetch_with_retries and sets `Access-Control-Allow-Origin: *` for responses.

Tips for contributors
- When adding or testing tiles, prefer small, stable image endpoints (NOAA, SWPC) to reduce flakiness.
- To debug CORS-linked failures, run `python server.py` and request tile URLs through `/proxy?url=`.
- If you need to change refresh behavior: update `IMAGE_REFRESH_RATE_MS` and call `refreshImages()` in the console to verify immediate effect.

Examples (from code)
- Change tile URLs: edit the `contentData` array near line ~70 in `Dashboard.html`.
- Use the proxy: `http://localhost:8000/proxy?url=https%3A%2F%2Fwww.hamqsl.com%2Fsolarpic.php` to fetch hamqsl content without CORS errors.

What NOT to change
- Avoid splitting `Dashboard.html` into multiple runtime files unless you update README and the run instructions. The project is intentionally zero-build.
- Do not hardcode API keys into the repo.

If something is unclear
- Tell me which file/line you want clarified (e.g., "Dashboard.html contentData lines around 60-100") and I will update this guidance.

----
Generated: automated pass — please review and request edits.
