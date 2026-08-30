# Language HQ

A personal "conductor" for a four-language self-study program (Norwegian, Spanish, Japanese; Chinese parked). It doesn't teach anything and doesn't integrate with the learning tools — it answers three questions with zero navigation:

1. **What do I do now?** Today's two blocks, each a fixed recipe with a link and a cursor.
2. **Did I do it?** One tap: Done / Floor / Skip; one tap for evening input hours.
3. **What did I get wrong?** A single field for an error pattern, kept as a running log.

It is a static, installable web app (PWA): no server, no accounts, no analytics, no build step. All data lives on the device in `localStorage`. The design decisions come from [BUILD-BRIEF.md](BUILD-BRIEF.md), which in turn is based on the evidence review in [research-report.md](research-report.md).

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app — markup and vanilla JS, including the preloaded plan |
| `styles.css` | The one stylesheet (mobile-first at 390 px, dark theme) |
| `manifest.webmanifest` | PWA manifest (installable, standalone display) |
| `sw.js` | Service worker — caches the app shell for offline use |
| `icons/` | 192/512 px PNG icons + 180 px `apple-touch-icon.png` |

## How to run

It's a static site, but the service worker needs HTTP (not `file://`). Serve the folder with any static server and open `http://localhost:<port>`:

```bash
python -m http.server 8000
```

or `npx serve`, or (Windows, no Node/Python) any static file server. Opening `index.html` directly from disk also works for everything except offline caching.

## How to publish

Everything uses relative paths, so it works from a subpath (e.g. `/language-hq/`).

**GitHub Pages:** create a repo (e.g. `language-hq`), upload this folder (or `git push`), then Settings → Pages → Deploy from branch → `main` / root. The site appears at `https://<user>.github.io/language-hq/`.

**Netlify Drop:** drag the folder onto <https://app.netlify.com/drop>.

**Install on iPhone:** open the published URL in Safari → Share → **Add to Home Screen**. It opens standalone and works offline after the first load.

## How to export / restore

- **Setup → Data → Download data.json** downloads the complete document (settings, resources, template, sessions, input log, errors, milestones, phases — everything).
- **Copy export** puts the same JSON on the clipboard.
- **Import** restores from a `data.json` file or pasted JSON. The document you're replacing is backed up under the localStorage key `language-hq.pre-import`.
- **Reset** (requires typing `RESET`) restores the preloaded plan; the old data is backed up under `language-hq.pre-reset`.

The schema is versioned (`schemaVersion`); imports run through `migrate()`, so older exports keep working after schema changes.

## Everyday use

- **Today** — the day's blocks with recipes, resource links, and cursors. Done/Floor/Skip stamp a session for today; tapping the same button again undoes it. The floor rule is shown on the page. Saturday shows the empty state; Sunday shows the two optional Sunday blocks.
- **Week** — Monday-first grid; tap a tile to cycle pending → done → floor → skipped. Completion, minutes, input hours, and error counts underneath.
- **Sunday** — copy buttons for the weekly summary and the three session prompts, the error-log manager, milestones, and the monthly-probe reminder on the first Sunday of the month.
- **Setup** — resources (link, cursor, active toggle, notes), template & recipe editor, phases, settings, export/import/reset.

## Choices the brief left open

Reasonable choices made during the build (per the brief's instruction to note them here):

- **Blocks carry a `resourceId`** (the block's primary resource, e.g. NO-chapter → NoW1) and an `optional` flag (the two Sunday blocks). The §3 schema didn't include either, but §5 assigns each block a resource and marks Sunday blocks optional.
- **Phases carry `activates` / `deactivates` / `optional` lists** — §4 says switching phases swaps active resources; Norwegian phases also flip Sunday speaking to non-optional (per §5 phase 2). Norwegian phases carry a `level` used in the session prompt (`Foundation` → A1–A2, `Build`/`Exam prep` → B1).
- **If a block's resource is deactivated by a phase swap**, the Today card falls back to the first *active* resource in the same language + lane (so NO-chapter shows NoW2 in phase 2). If none is active, the resource row is hidden — inactive resources never appear on Today.
- **Floor stamps 10 minutes** (matching the stated floor rule), Done stamps the block's minutes, Skip stamps 0. Historical sessions keep their stamped minutes if you later edit block minutes.
- **Optional blocks** don't count against the week's completion rate until you interact with them: they enter both numerator and denominator only once a session exists.
- **"Monologues recorded"** in the weekly summary = NO-chapter sessions marked Done that week (the monologue is a step of that recipe; Floor omits it).
- **Session notes**: a small note field appears on a block card once a status is set; notes flow into the weekly summary's `Notes:` line.
- **`{task}` in the Norwegian prompt** is left literal for you to replace with the muntlig task you're rehearsing; `{level}` is filled from the active Norwegian phase.
- **Resources with no URL in the brief** (podcasts, books, the Chinese apps) are shown without links; Anki entries all link to ankiweb.net.
- **NoW2 is seeded with a `chapter 1` cursor** even though the brief lists it without one: it's the phase-2 course and there is deliberately no "add a cursor" UI, so it ships ready to track.
- **`langId` is `null` on SUN-review** (and its recipe) — it's a cross-language block, shown in neutral gray. Chinese ships with `phase: null` since the brief defines no Chinese phases.
- **Dates use the device clock.** The `timezone` setting is stored but informational. For testing or backfilling, `?date=YYYY-MM-DD` in the URL makes Today render as that date.
- **Weekly summary weeks are Monday–Sunday** (or Sunday-first if you untick "Week starts Monday" — the summary header follows the same week window).
- **Corrupt or unreadable stored data is never discarded**: it's stashed under `language-hq.corrupt` before the app re-seeds.

## Development

See [CLAUDE.md](CLAUDE.md) for project conventions — above all: **the schema is versioned; every change to it needs a migration.**
