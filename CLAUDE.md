# Language HQ — project conventions

Personal PWA "conductor" for a four-language self-study program. Spec: [BUILD-BRIEF.md](BUILD-BRIEF.md). Rationale: [research-report.md](research-report.md).

## The one rule

**The schema is versioned; every change to it needs a migration.**

All user data is one JSON document in `localStorage` under the key `language-hq`, stamped with `schemaVersion` (currently 1). If you change the shape of that document in any way — add/rename/remove a field, change a type, restructure an array:

1. Bump `SCHEMA_VERSION` in `index.html`.
2. Add a step to `migrate()` that transforms version N documents to N+1 in place. Migrations run in order, so old exports and old devices always come forward cleanly.
3. Update `seed()` to produce the new version directly.
4. Never write a migration that can drop user data. Unknown fields are preserved; unreadable data gets stashed under `language-hq.corrupt`, never deleted.

`migrate()` also runs on every import, so exported `data.json` files from any past version must keep importing.

## Architecture

- **No build step, no frameworks, no external runtime dependencies.** `index.html` holds all the JS; `styles.css` is the one stylesheet. Keep it that way.
- Static files only: `index.html`, `styles.css`, `manifest.webmanifest`, `sw.js`, `icons/`.
- **All paths are relative** (`./…`) so the site works under a subpath like `/language-hq/` on GitHub Pages. Don't introduce absolute paths.
- `sw.js` caches the app shell (cache-first). **Bump `CACHE_VERSION` in `sw.js` whenever any shell file changes**, or installed clients keep serving the old version.
- Rendering: each view is a pure `render*()` function returning an HTML string; interaction is delegated document-level listeners keyed on `data-act` (clicks) and `data-chg` (change events). Every mutation calls `save()` — write on every change.
- All user-entered text goes through `escapeHtml()` before being interpolated into HTML.

## Conventions

- Mobile first: layout must be good at 390 px wide (iPhone), then desktop. Tap targets ≥ 44 px, real `<button>`s, visible focus, labels on inputs, `prefers-reduced-motion` respected.
- Prefer fewer features done well. No login, no notifications, no charts beyond simple counts, no analytics.
- Dates are local-device `YYYY-MM-DD` strings; weeks are Monday-first by default (`settings.weekStartsMonday`).
- Schema extensions beyond the brief's §3 (all documented in README.md): `blocks[].resourceId`, `blocks[].optional`, `phases[].activates/deactivates/optional/level`.
- Seed content in `seed()` must match BUILD-BRIEF.md §5 exactly; prompt texts must match §7 exactly; the weekly summary must match the §6 format.

## Testing

- Serve over HTTP (any static server) — the service worker doesn't register from `file://`.
- `?date=YYYY-MM-DD` on the URL makes the app treat that date as "today" (e.g. `?date=2026-08-31` to see a Monday).
- Manual checklist = BUILD-BRIEF.md §9: fresh-load Monday blocks, persistence across reloads, export/import round-trip, offline open, no console errors.
