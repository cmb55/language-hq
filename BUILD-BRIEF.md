# Language HQ — build brief for Claude Code

Read this whole file before writing code. Then build the app described here, run it in the preview so you can see it working, and fix what you see. Ask me only if something below is contradictory; otherwise make reasonable choices and note them in README.md.

`research-report.md` in this folder is the evidence review and resource survey the design is based on. Use it as reference when a question of "why" comes up; the decisions below already reflect it.

## 1. What this is

A personal "conductor" for a four-language self-study program (Norwegian, Spanish, Japanese; Chinese parked). It does not teach anything and does not integrate with the learning tools. It answers three questions with zero navigation:

1. What do I do now? (today's two blocks, each a fixed recipe with a link and a cursor)
2. Did I do it? (one tap: done / floor / skipped; one tap for evening input hours)
3. What did I get wrong? (a single field for an error pattern, kept as a running log)

Primary device: iPhone, installed to the home screen from Safari. Secondary: desktop browser. Data lives on the device; no server, no accounts, no analytics.

## 2. Technical requirements

- Single static site with no build step: `index.html` (vanilla JS, CSS in the same file or one `styles.css`), `manifest.webmanifest`, `sw.js` (service worker that caches the app shell for offline use), `icons/` (192 and 512 px PNG, plus `apple-touch-icon.png` 180 px). No frameworks, no bundler, no external CDN dependencies at runtime.
- Installable on iOS Safari via Add to Home Screen: `display: standalone`, theme color, `apple-mobile-web-app-capable`, apple-touch-icon. Layout must be good at 390 px wide first, then desktop.
- Storage: `localStorage` under one key holding a single JSON document (schema in §3), versioned with a `schemaVersion` and a `migrate()` function. Write on every change. Never lose data on a schema change.
- Export/import: "Download data.json" (file download) and "Copy export" (clipboard), plus "Import" via file picker or pasted JSON. Export must include everything.
- Accessibility floor: real `<button>`s, visible focus, labels on inputs, `prefers-reduced-motion` respected, tap targets ≥ 44 px.
- Keep it small and legible. Prefer fewer features done well. No login, no notifications (I'll use the iPhone's own Clock/Calendar for reminders), no charts beyond simple counts.
- Write `README.md` (what it is, how to run, how to publish, how to export/restore) and `CLAUDE.md` (project conventions and the rule: "the schema is versioned; every change to it needs a migration").

## 3. Data model (one JSON document)

```
{
  schemaVersion: 1,
  settings: { weekStartsMonday: true, timezone: "America/Chicago" },
  languages: [ { id, name, code, color, tier: "build"|"push"|"maintain"|"parked", phase: id, current: string, target: string } ],
  resources: [ { id, langId, lane: "course"|"srs"|"input"|"output"|"exam"|"reference", name, url, cursor: { label, value }, active: bool, notes } ],
  recipes: [ { id, langId, name, steps: [ { minutes, text, resourceId? } ] } ],
  template: { mon: [blockIds], tue: [...], ..., sun: [...] },
  blocks: [ { id, label, langId, recipeId, minutes } ],
  sessions: [ { id, date: "YYYY-MM-DD", blockId, status: "done"|"floor"|"skipped", minutes, note } ],
  inputLog: [ { id, date, langId, minutes, note } ],
  errors: [ { id, langId, text, opened: date, closed: date|null } ],
  milestones: [ { id, langId, date, text } ],
  phases: [ { id, langId, name, startsWhen: string, active: bool } ]
}
```

Cursor semantics: a cursor is a label plus a value the user advances by one tap (e.g. `{ label: "chapter", value: 4 }` or `{ label: "episode", value: "S15E03" }`). Numeric cursors get an arrow button; string cursors get an editable field.

## 4. Surfaces (in order of how often they're opened)

### Today (home)
- Date, weekday, current phase per active language in small text.
- The day's blocks from the template. Each block card shows: language color bar, label, total minutes, the recipe steps (with minutes), the linked resource name as a tappable link that opens the resource in a new tab, and the cursor with an advance control.
- Controls per block: **Done**, **Floor** (counts as complete at reduced load), **Skip**. Done/Floor stamp a session for today. Tapping again undoes.
- One text field at the bottom: "Error pattern" with a language picker, Enter to save. Below it, the three most recent open errors.
- Evening input: three buttons "+30 Spanish", "+30 Japanese", "+30 Norwegian" and a small custom-minutes field. Shows today's input total.
- Empty weekend state: "Nothing scheduled. Evening input still counts." Sunday shows the Sunday block if enabled.

### Week
- Seven columns, Monday first, today highlighted. Tiles per block: filled when done, half-filled when floor, outlined when pending, struck when skipped. Tap toggles status.
- Under the grid: completion rate for the week (done + floor over scheduled), per-language minutes, input hours per language this week, errors opened/closed this week.
- Previous/next week navigation.

### Sunday
- **Copy weekly summary**: plain text, format in §6.
- **Copy Norwegian session prompt**: exact text in §7, with the current phase's level inserted.
- **Copy Spanish correction prompt** and **Copy Japanese output prompt** (texts in §7).
- Error log manager: list of open errors with a Close button and a date; closed errors collapsed below.
- Milestones: add/remove with date.
- Monthly probe reminder on the first Sunday of the month (text only, from §5).

### Resources and settings
- Resources grouped by language then lane, with name, link, cursor, active toggle, notes. Inactive resources hidden from Today.
- Template editor: which blocks on which weekday; block minutes; recipe step editor (simple: list of minutes + text).
- Phases: list per language with active toggle; switching the active phase can swap which resources are active (implement as: each phase lists resource ids to activate/deactivate).
- Export / Import / Reset (Reset requires typing RESET).

## 5. Preloaded content (ship exactly this as the initial state)

### Languages
- Norwegian (Bokmål), code NO, tier build, current "A0", target "A2 oral (permanent residence), then B1 oral (citizenship)". Phase 1 active.
- Spanish, code ES, tier push, current "B1–B2 (placement pending)", target "C2 (DELE)". Phase 1 active.
- Japanese, code JA, tier maintain, current "~N3 (placement pending)", target "N2, then N1". Phase 1 active.
- Chinese, code ZH, tier parked, current "dormant (was ~A1)", target "reactivate when Norwegian reaches A2". No blocks.

### Template (Mon–Fri two blocks; Sunday optional)
- Mon: NO-chapter, ES-input
- Tue: NO-chapter, JA-read
- Wed: NO-chapter, ES-output
- Thu: NO-chapter, JA-grammar
- Fri: NO-consolidate, ES-precision
- Sat: none
- Sun: SUN-norwegian-speaking (15) and SUN-review (15), both marked optional in the UI

### Blocks and recipes (minutes in parentheses)
- **NO-chapter** (30): Anki reviews, new cards capped at 10/day (8) · NoW chapter: read the text with audio, one grammar point (12) · Shadow the chapter audio twice, then record a 60–90 s monologue on the chapter topic; save it to the island bank (10). Resource: NoW1 (cursor: chapter).
- **NO-consolidate** (30): Pronunciation: minimal pairs from the week's words, listen to 5+ different speakers on Forvo, then record yourself (10) · Re-record the week's best monologue and compare with the first take (10) · Anki reviews plus a pass through open Norwegian error patterns (10). Resource: Forvo.
- **ES-input** (30): Radio Ambulante or El Hilo segment with the transcript (20) · 5–8 sentences into Anki as sentence cards (10). Resource: Radio Ambulante (cursor: episode).
- **ES-output** (30): Write 150–200 words on Monday's topic (15) · Post to LangCorrect; quick pass with Claude using the correction prompt; log one error pattern (15). Resource: LangCorrect (cursor: entries).
- **ES-precision** (30): Kwiziq lessons and kwiz (15) · Drill open Spanish error patterns; Anki reviews (15). Resource: Kwiziq (cursor: level, string).
- **JA-read** (30): Anki reviews (10) · Satori Reader episode with audio, read aloud once (20). Resource: Satori Reader (cursor: episode, string).
- **JA-grammar** (30): Bunpro reviews (10) · NHK News Web Easy article or one podcast segment (12) · Record a 90 s summary, or write 5 lines to Claude with the output prompt (8). Resource: Bunpro (cursor: JLPT level, string).
- **SUN-norwegian-speaking** (15): Rehearse one Norskprøven muntlig task with Claude (voice if Norwegian is available, otherwise typed); paste the session prompt; log one error pattern.
- **SUN-review** (15): Copy the weekly summary into the Claude project; set next week's cursors; close any error pattern that stayed clean for two weeks.

Floor rule shown on Today: "Floor = Norwegian Anki reviews + one NoW text read aloud (10 min). Counts as a completed day."

### Resources (lane, name, url, initial cursor)
Norwegian: course · Norwegian on the Web 1 · https://www.ntnu.edu/now · chapter 1 | course (inactive until phase 2) · NoW2 · https://www.ntnu.edu/now2 | srs · Anki (AnkiMobile + AnkiWeb) · https://apps.ankiweb.net | input · Norsk for Beginners (podcast) · episode 1 | input (inactive until phase 2) · Lær norsk nå! · episode 1 | input (inactive until phase 2) · Klar Tale · https://www.klartale.no | reference · Forvo · https://forvo.com | reference · Ordbøkene · https://ordbokene.no | exam · HK-dir Norskprøven samples and registration · https://prove.hkdir.no | exam (inactive until phase 3) · muntlig.com · https://muntlig.com
Spanish: course · Kwiziq Spanish · https://spanish.kwiziq.com · level "placement pending" | srs · Anki | input · Radio Ambulante · https://radioambulante.org · episode "latest" | input · El Hilo · https://elhilo.audio | output · LangCorrect · https://langcorrect.com · entries 0 | exam · Instituto Cervantes DELE models · https://examenes.cervantes.es | exam (inactive until phase 2) · El Cronómetro C2 (book) | exam · SIELE · https://siele.org
Japanese: course · Bunpro · https://bunpro.jp · level "placement pending" | srs · Anki + Yomitan | input · Satori Reader · https://www.satorireader.com · episode "choose a series" | input · NHK News Web Easy · https://www3.nhk.or.jp/news/easy/ | input · YUYU Nihongo Podcast | exam · JLPT official samples · https://www.jlpt.jp/e/ | exam (inactive until phase 2) · Shin Kanzen Master (book)
Chinese (all inactive): HelloChinese, Du Chinese, Pleco, Anki HSK deck.

### Phases
Norwegian: Phase 1 "Foundation" (months 1–3: NoW1, Norsk for Beginners, Anki new cards ≤10/day) · Phase 2 "Build" (starts when NoW1 is finished: NoW2, Lær norsk nå!, Klar Tale; Sunday speaking becomes non-optional) · Phase 3 "Exam prep" (starts 4 weeks before a Norskprøven sitting: muntlig.com pass, full mocks, NRK for dialects).
Spanish: Phase 1 "To C1" (Kwiziq until it reports C1) · Phase 2 "C1→C2" (Kwiziq slot becomes El Cronómetro tasks; SIELE benchmark).
Japanese: Phase 1 "Maintain" · Phase 2 "JLPT prep" (starts 4 months before a sitting: add Shin Kanzen Master).

### Milestones and dates (pre-seed)
- 2026-09-10: decide on JLPT December sitting (US registration closes Sep 16; N3 is the low-stakes anchor).
- 2026-09-13: week-2 keep-or-kill: Kwiziq, Satori Reader, LangCorrect, Norsk for Beginners.
- 2026-09-25: DELE decision (register by Sep 30 or target May 2027).
- 2026-09-27: month-1 review.
- Monthly probe (first Sunday): NO one HK-dir sample task timed; ES one Cervantes model task; JA one JLPT sample section.

## 6. Weekly summary format (plain text, for pasting into Claude)

```
Week of {Mon date} – {Sun date}
Completion: {done+floor}/{scheduled} blocks ({pct}%), floors: {n}, skips: {n}
Norwegian: {blocks done}/{scheduled}, {min} min · cursor: NoW1 ch {n} · monologues recorded: {n}
Spanish: {done}/{scheduled}, {min} min · input this week: {h} h · Kwiziq: {level} · LangCorrect entries: {n}
Japanese: {done}/{scheduled}, {min} min · input: {h} h · Satori: {episode} · Bunpro: {level}
Errors opened: {list} | closed: {list}
Milestones: {list}
Notes: {session notes concatenated}
Ask: propose next week's cursors and one precision focus per language.
```

## 7. Prompt texts (copy buttons)

Norwegian session prompt:
"Vi snakker bare norsk (bokmål). Hold deg på nivå {level}. Still oppfølgingsspørsmål og ikke rett meg underveis. Vi øver på én oppgave fra Norskprøven muntlig: {task}. Etter 15 minutter: en liste «Corrections» på engelsk — min setning → rettet setning → regelen, én linje hver — og oppgi hvor jeg kan sjekke regelen (NoW-kapittel eller ordbokene.no). Dersom du er usikker på en regel, si det."
(English note under the button: "If Norwegian voice isn't available, run this typed.")

Spanish correction prompt:
"Corrige este texto como examinador DELE C1. Primero la versión corregida completa; luego una tabla original → corrección → regla; al final, un solo patrón que debo añadir a mi registro de errores. Si no estás seguro de una regla, dilo."

Japanese output prompt:
"今日読んだ内容について要約を書きます。N2レベルで直してください。最後に、覚えるべきパターンを一つだけ教えてください。規則に自信がない場合はそう言ってください。"

## 8. Publishing

After the app works in the preview:
1. Initialise a git repo, commit.
2. If the GitHub CLI is available and authenticated, create a public repo `language-hq`, push, and enable GitHub Pages from the main branch root; print the Pages URL. If not, tell me the two manual options: upload the folder in the GitHub web UI and enable Pages in Settings → Pages, or drag the folder onto Netlify Drop.
3. Confirm the service worker and manifest serve correctly from the Pages URL (paths must be relative so it works under `/language-hq/`).
4. Print the iPhone install steps: open the URL in Safari → Share → Add to Home Screen.

## 9. Definition of done

- Fresh load shows Monday's two blocks with recipes, cursors and working links.
- Done/Floor/Skip, cursor advance, input buttons, error field, week grid, all persist across reloads.
- Export produces a complete JSON; import restores it; schema is versioned.
- Installs to an iPhone home screen and opens offline.
- README and CLAUDE.md exist. No console errors.
