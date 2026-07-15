# SORT — Project Board

Single-file web app (`index.html`, ~2500 lines): HTML/CSS/vanilla JS, no build step, no framework, no package.json.

## Structure
- All markup, styles, and script are inline in `index.html`.
- Timeline view: 40 half-month slots across ~20 months (`MONTHS_META`, `TOTAL_SLOTS`).
- Categories: space, legal, brand, inventory, staffing, community, digital — plus user-defined custom categories (stored in `localStorage` under `sort_custom_cats`).
- Tasks support subtasks and comments.

## Backend
- Supabase (Postgres + REST) via direct `fetch` calls — see `SB_URL`/`SB_KEY`/`SB_HDR` and the `sb*` functions (`sbInit`, `sbCreateSubtask`, `sbUpdateSubtask`, `sbDeleteSubtask`, etc.).
- The embedded key is the Supabase anon/public key (expected to be client-visible; access control is via Supabase RLS policies, not key secrecy).

## Running locally
No build tools required. Open `index.html` directly in a browser, or serve the folder with any static file server (e.g. `python3 -m http.server`).

## Working conventions
- Keep everything in the single `index.html` file unless the user asks to split it up.
- No test suite or linter configured yet.
