# Building a Multi-Language Self-Study Program: Method Review and Resource Survey (August 2026)

## TL;DR
- **The evidence-backed core of your program should be: (1) comprehensible input at scale, (2) spaced retrieval practice with an SRS, (3) explicit grammar as a fast scaffold, and (4) deliberate speaking output with feedback — for Norwegian, most of your effort should go to structured speaking rehearsal of the Norskprøven *muntlig* format, not app-based vocabulary grinding.** Academic SLA research and long-term-learner communities converge strongly on input + retrieval + output; they diverge mainly on how much explicit grammar and how early to speak, which the reconciliations below resolve.
- **Your one-resource-per-lane stack:** Norwegian — NTNU's free *Norwegian on the Web* (NoW1/NoW2) + Anki + *Lær norsk nå!* podcast + an AI speaking partner (Claude, plus optionally muntlig.com) + HK-dir official sample tests. Spanish — Kwiziq (grammar to C1) + Anki + Radio Ambulante/El Hilo + LangCorrect + El Cronómetro C2 with free Instituto Cervantes past papers. Japanese — Bunpro/Renshuu + Anki-with-Yomitan + Satori Reader/NHK News Web Easy + self-recording + Shin Kanzen Master. Anki is the single SRS to run all three languages.
- **Highest-leverage, most-overlooked moves:** treat the Norskprøven *muntlig* as a *format-rehearsal* problem (drill the four tasks and "repair phrases" until automatic), adopt High-Variability Phonetic Training for Norwegian sounds early, and use AI (Claude) as a conversation partner with a persistent error log — but verify its grammar claims, because LLMs produce fluent-but-wrong corrections and drift out of the target language.

---

# PART 1 — METHOD REVIEW (Academic Evidence vs. Learner-Community Consensus)

## 1. Spaced repetition and retrieval practice for vocabulary

**(a) Research.** This is among the best-supported findings in learning science. Kim & Webb's meta-analysis (*Language Learning* 72:269–319, 2022) synthesized 98 effect sizes from 48 experiments (N = 3,411) and found robust benefits of spaced over massed practice for L2 learning. The same meta-analysis found **large effects of immediate feedback (g = 1.04, 95% CI [0.59, 1.49]) and delayed feedback (g = 0.64–2.34)** on L2 vocabulary retention, with the immediate–delayed difference *not* statistically significant — i.e., feedback timing matters far less than the fact of spaced retrieval itself (consistent with Nakata's small d = 0.14 timing effect on delayed receptive recall). Retrieval practice (active recall) is a distinct, additive mechanism: recalling a word beats re-studying it (Nakata 2017, *SSLA*; Nakata, Tada, McLean & Kim 2021, *TESOL Quarterly*, on cumulative testing). On card format, the incidental-vocabulary-from-repetition literature (a meta-analysis found a medium effect, r = .34) supports learning words in context.

**(b) Community.** Overwhelming consensus around Anki. Refold and The Moe Way advocate "sentence mining" — pulling sentences with one unknown word ("1T"/i+1) from immersion into personalized cards. Community nuance converges on: word cards to build a ~1,000-word base, then sentence cards; frequency-ordered pre-made decks (e.g., Kaishi 1.5k for Japanese, which superseded the older Core 2k/6k and Tae Kim decks) to bootstrap; and strict card-count discipline (10–20 new/day early) to avoid review-pile burnout.

**(c) Verdict: Strongly supported.** Reconciliation: SRS is a *reinforcement* tool, not a primary *acquisition* tool (community phrasing) — it consolidates what input introduces. Sentence mining is well-motivated by context/i+1 principles but time-expensive; for a 5–10 hr/week learner, curated frequency decks plus light mining is the efficient path.

## 2. Comprehensible input at scale

**(a) Research.** Extensive reading has consistent meta-analytic support: **Nakanishi (2015, *TESOL Quarterly* 49(1):6–37) analyzed 34 studies / 43 effect sizes / N = 3,942, finding a medium effect for group contrasts (d = 0.46) and a larger pre–post effect (d = 0.71)**, with benefits that grow with program length; a 2025 *Educational Psychology Review* meta-analysis reaffirmed reading's impact. The lexical-coverage literature (Laufer; Nation; Schmitt) establishes ~95% coverage as the minimum and ~98% as optimal for comprehension and incidental learning — the empirical basis for "make input comprehensible." However, Krashen's strong claim that comprehensible input is *sufficient* (and output/grammar unnecessary) is contested: Spada & Tomita (2010) show explicit instruction adds value, and a 2025 *Frontiers in Psychology* "neuro-ecological critique" argues interaction and output also matter.

**(b) Community.** The biggest recent shift in practice. Dreaming Spanish popularized a pure-CI roadmap; **per its official "Language Learning Roadmap" (v1.3, Jan 2025) the seven levels map to input hours: Level 1 = 0h, Level 2 = 50h, Level 3 = 150h, Level 4 = 300h, Level 5 (understand normal speech) = 600h, Level 6 (comfortable daily conversation) = 1,000h, Level 7 (overall effective user) = 1,500h.** Refold builds its whole method on an input-first foundation. Consensus: massive input is non-negotiable for fluency and listening.

**(c) Verdict: Strongly supported (as necessary); contested (as sufficient).** Input is the engine; the "input-only, never output" position is not tenable for someone with a near-term *speaking* exam. Reconciliation: prioritize input for volume and listening, but do not defer speaking — you need output practice for the Norskprøven.

## 3. Output with corrective feedback (including AI chat/voice)

**(a) Research.** Corrective feedback has meta-analytic support (Li 2010, oral CF; Van Beuningen, De Jong & Kuiken 2012, written CF). The output hypothesis (Swain) holds that production forces deeper processing. On LLMs specifically, a systematic review of 30 studies (2020–2024, *Heliyon*/ScienceDirect) found chatbots improved productive skills, especially speaking and writing, via real-time feedback and anxiety reduction. Kim (2024, *Language Learning & Technology* 28(2):109–133) found AI-chatbot corrective recasts produced significant learning gains when learners successfully "uptook" the correction. Kamelabad et al. (an "in-the-wild" study of 65–66 L2 English learners) found immediate vs. delayed chatbot feedback produced no significant difference in learning gains, though immediate feedback improved user experience. **Documented failure modes:** LLMs generate "fluent but incorrect" feedback (the Hattie & Timperley fluency-as-correctness trap; Kakarla et al. 2024), sometimes fail to determine whether an answer is even wrong, and human tutors still outperform them at adapting to misconceptions (Wang et al. 2024).

**(b) Community.** Rapid, enthusiastic adoption of ChatGPT/Claude as always-available conversation partners and error-loggers. Reported failure modes match the literature: over-correction of natural-but-informal usage, hallucinated grammar "rules," inconsistent target-language fidelity (drifting into English or over-formal register), and unreliable pronunciation feedback from text-only models.

**(c) Verdict: Supported, with caveats.** Reconciliation: use AI as a *sparring partner and error-logger*, not an *authority* — cross-check grammar claims against a reference, and pin the target language/register explicitly in your prompt.

## 4. Shadowing, chorusing, self-recording, pronunciation training

**(a) Research.** High-Variability Phonetic Training (HVPT) is "increasingly considered the most empirically supported phonetic training paradigm in L2 speech research." **Uchihara, Karas & Thomson (2025, *Studies in Second Language Acquisition* 47(3):794–827), a meta-analysis of 79 studies, found: "The overall medium-to-large effects of HVPT on L2 speech perception support the effectiveness of HVPT, for both pretest-posttest comparison (g = 0.92, k = 96) and treatment-control comparison (g = 0.67, k = 32)," with long-term retention and some transfer to novel stimuli.** Thomson's (2018, *Journal of Second Language Pronunciation*) synthesis of 32 studies reached the same conclusion. Shadowing: **Whitworth's "A Systematic Review of Research on the use of Shadowing for Second Language Pronunciation Teaching" (Taylor & Francis, online 1 Sep 2025), covering 44 studies, found "shadowing training can help improve learners' comprehensibility, intelligibility, and accentedness, as well as certain aspects of suprasegmental pronunciation control, such as fluency and prosody"** (segmental effects were inconclusive).

**(b) Community.** Shadowing and self-recording are staples; HVPT is under-known but growing. Communities strongly endorse recording yourself and comparing to native audio.

**(c) Verdict: Strongly supported (HVPT); supported (shadowing/self-recording).** Highly relevant to an oral exam. Reconciliation: HVPT for perceptual accuracy of tricky Norwegian sounds early; shadowing + self-recording for prosody and fluency throughout.

## 5. Explicit grammar vs. implicit acquisition (intermediate–advanced)

**(a) Research.** Three large meta-analyses — Norris & Ortega (2000), Spada & Tomita (2010, *Language Learning* 60(2):263–308), Goo et al. (2015) — consistently find explicit instruction produces larger effect sizes than implicit for both simple and complex features, on both controlled and freer-production measures. The main critique (including from Spada herself, 2014) is that the tests may over-measure explicit knowledge rather than the implicit knowledge underlying spontaneous communication.

**(b) Community.** Refold and CI purists downplay grammar as a light "reference" to speed noticing; more traditional communities (r/LearnJapanese around Bunpro, r/Spanish) value structured grammar. Convergence: "grammar-light but not grammar-free" — study a point, then find it in input.

**(c) Verdict: Supported (explicit grammar as accelerator).** Reconciliation: for adults, explicit grammar speeds acquisition, especially of complex morphology (Norwegian V2 word order, Spanish subjunctive, Japanese particles). Use it as a scaffold that points you at input, not as the main event.

## 6. Interleaving and scheduling; multiple languages concurrently

**(a) Research.** The distributed-practice/spacing effect is among the most robust findings in cognitive psychology (Cepeda et al.): the same total time yields more retention spread across days than massed — direct support for daily short sessions over occasional long ones. Interleaving (mixing topics/skills) generally aids discrimination and durable learning. Morning-vs-evening evidence is weak and individual; sleep consolidation supports studying before sleep. On concurrent languages, direct experimental evidence is thin; cross-linguistic interference is real mainly between *typologically similar* languages, and time-dilution is the bigger practical risk.

**(b) Community.** Strong consensus for daily consistency over cramming. Polyglot consensus on multiple languages: feasible, but keep them at *different levels* or *different scripts* and give one clear priority.

**(c) Verdict: Strongly supported (daily short sessions, spacing); supported (interleaving); reconciled (multi-language feasible with priority).** Your plan — daily 30-min Norwegian, alternating Spanish/Japanese — is well-designed. Norwegian (Germanic), Spanish (Romance), and Japanese (Japonic) are typologically distant enough to minimize interference; the real constraint is time, so Norwegian's priority is correct.

## 7. Habit and adherence design for long-horizon self-study

**(a) Research.** Habit-formation research (Lally et al.) shows behaviors automate through consistent context-cued repetition over ~2 months; "minimum viable" actions lower activation energy. Implementation intentions ("after X, I do Y") reliably increase follow-through. Goal-setting research favors tracking *process/leading* indicators over distant *outcome/lagging* ones for motivation.

**(b) Community.** Streaks are double-edged: motivating but can incentivize hollow reps (the "Duolingo streak" critique). Consensus favors a small non-negotiable daily minimum, tracking input hours (Dreaming Spanish-style), and reviewing error patterns.

**(c) Verdict: Supported.** Reconciliation: anchor sessions to your fixed morning block (implementation intention), define a minimum viable session ("10 Anki reviews counts"), track leading indicators (sessions completed, input hours, recurring errors), and use exams only as periodic lagging checkpoints.

## 8. Preparing specifically for oral proficiency exams (Norskprøven *muntlig*)

**(a) Research.** Task-repetition/rehearsal research shows repeated practice of a task type improves fluency and complexity on that task; test-format familiarity reduces construct-irrelevant anxiety. HVPT and shadowing (above) transfer to oral performance.

**(b) Community.** The r/norsk and immigrant-learner consensus: the *muntlig* is passable through *format rehearsal* — "island"/prepared-module strategies (pre-built chunks on family, work, hobbies, environment), drilling the four tasks, and rehearsing "repair phrases"/time-buyers to keep talking. AI speaking tools (muntlig.com, norskproven.ai) are widely used to get reps.

**(c) Verdict: Supported/strongly supported for format rehearsal.** Reconciliation: at A2/B1, most speaking practice *can* be self-generated without a tutor — via AI partners, self-recording, and prepared "islands" — provided you rehearse the actual exam format. This is the crux of your Norwegian plan.

## 9. Weak or contested methods communities often over-rate

**(a) Research.** *Passive/background listening* to incomprehensible audio has little support — comprehension is required for acquisition (the 95–98% coverage literature); noise you can't parse doesn't teach. *"Learn while you sleep"* (hypnopaedia) is essentially debunked for new linguistic material; sleep *consolidates* prior learning but doesn't teach new content. *Gamified apps past the beginner stage* plateau — fine for streaks and basics, but lacking the depth, output, and authentic input needed from intermediate up.

**(b) Community.** Broad agreement that Duolingo is "overrated past the beginning," that background listening is at best ambient prosody exposure, and that sleep-learning is a myth.

**(c) Verdict: Weak/contested evidence.** Reconciliation: passive listening has marginal value only for *already-comprehensible* material; treat gamified apps as beginner on-ramps to abandon; ignore sleep-learning.

## 10. Genuinely newer or unique methods worth a trial

- **AI conversation tools with persistent error logs** (Claude, ChatGPT; Norwegian-specific muntlig.com/norskproven.ai) — 2023–2026 evidence is early but positive for output reps and immediate feedback; trial with verification discipline. **Supported (emerging).**
- **Immersion toolchains** (Yomitan pop-up dictionary + AnkiConnect one-click mining; Migaku for subtitle mining) — mature, community-validated for Japanese. **Supported.**
- **Comprehensible-input video libraries** (Dreaming Spanish; Comprehensible Japanese; nascent Norwegian CI) — grounded in the input/coverage research; the strongest new product category. **Supported.**
- **Graded-reader ecosystems** (Satori Reader for Japanese; LingQ across languages) — align with extensive-reading evidence. **Supported.**
- **HVPT trainers** — strong evidence but few polished consumer products. **Supported but tooling-limited.**

### Part 1 Summary Table of Verdicts

| Practice | Verdict |
|---|---|
| 1. Spaced repetition / retrieval practice | **Strongly supported** |
| 2. Comprehensible input at scale | **Strongly supported (necessary); contested (as sufficient)** |
| 3. Output + corrective feedback (incl. AI) | **Supported, with caveats** |
| 4. Shadowing / self-recording / HVPT | **Strongly supported (HVPT); supported (shadowing)** |
| 5. Explicit grammar instruction | **Supported (as accelerator)** |
| 6. Daily short sessions / interleaving / multi-language | **Strongly supported (spacing); supported (rest)** |
| 7. Habit & adherence design | **Supported** |
| 8. Oral-exam format rehearsal (self-generated) | **Supported / strongly supported** |
| 9. Passive listening / sleep-learning / late gamified apps | **Weak / contested** |
| 10. AI logs, immersion toolchains, CI libraries, graded readers | **Supported (several emerging)** |

---

# PART 2 — RESOURCE SURVEY

## NORWEGIAN (Bokmål) — top priority, zero → A2 oral → B1 oral

**Exam reality (verify on official sites).** Since 1 September 2025, the Norskprøven *muntlig* (oral) is the decisive language requirement — A2 oral for permanent residence, B1 oral for citizenship. It is a ~20–30 minute paired exam (two candidates, two examiners — one leads, one assesses), graded individually against CEFR. Structure: short introduction; an individual describe/tell task; a longer paired conversation; an individual opinion task. You can register for the oral section alone and for any level directly (the result reflects whatever level the examiner assesses). Assessment uses HK-dir's *vurderingsskjema* with criteria like answering the task understandably ("på en lett forståelig måte") and sustaining a conversation independently ("selvstendig"). Official sample tasks and a demo test are free on prove.hkdir.no ("Øv til norskprøven") and the Enovate voxdemo. The exam tests language, not knowledge — there is no fixed syllabus, and official questions are never published.

### Lane A — Structured course/curriculum

| Candidate | Status/maintenance | Platforms | Level | Structure | Transcripts/audio | Feedback | Export | Price | Exam align | Score | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **NTNU Norwegian on the Web (NoW1/NoW2)** | Active, NTNU-backed; NoW3 in development | Web | NoW1 ~A1–A2; NoW2 ~B1 | 10 chapters, clear progression, grammar + audio | Yes (texts + audio) | No | No | **Free** | Indirect (builds skills) | **9/10** | **Top pick** |
| **LearnNoW (NTNU/Vox)** | Active, free, institution-backed | Web | A1–B1 | Structured beginner course | Yes | Some auto-checked exercises | No | Free | Indirect | 8/10 | Strong |
| **FutureLearn "Learn Norwegian: Beginners 1 & 2"** | Active (NTNU-authored MOOC) | Web/app | A1–A2 | Guided weeks | Yes | Peer/quiz | No | Free to access (cert paid) | Indirect | 7/10 | Good on-ramp |

*Also considered/rejected:* **Babbel Norwegian** — well-structured beginner course built by in-house linguists, but a finite course you outgrow; paid. **Duolingo Norwegian** — fine for zero-start basics/streaks, weak past beginner. **Textbook series** (*På vei* → *Stein på stein* → *Her på berget*; *Norsk nå!*): the standard adult-education Bokmål progression, usable for self-study (esp. *På vei* with workbook/audio); *Mystery of Nils* and Routledge *Complete Norwegian* are self-study-friendly. Rejected as *primary* only because NoW is free and equivalent.

### Lane B — SRS / vocabulary

| Candidate | Status | Platforms | Notes | Export | Price | Score | Verdict |
|---|---|---|---|---|---|---|---|
| **Anki** | Active, stable for years | iOS/Android/desktop/web, offline | Frequency deck + mined cards; full control | **Yes (full export)** | Free (except $25 iOS app) | **9/10** | **Top pick** |
| **LingQ** (vocab side) | Active | All platforms | Auto-SRS from imported texts; good Norwegian library | Partial (vocab export) | ~$12–14/mo | 7/10 | If you live in LingQ |
| **Memrise Norwegian** | Active but degraded (AI-pivoted) | All | Variable quality; some words lack audio | Limited | Freemium | 5/10 | Weak |

### Lane C — Input (reading/listening/video)

| Candidate | Status | Level | Transcripts/audio | Price | Score | Verdict |
|---|---|---|---|---|---|---|
| **Lær norsk nå!** (podcast + site) | Active (episodes through mid-2026) | B1–B2 | **Yes — free transcripts on site** | Free (Patreon optional) | **9/10** | **Top listening pick** |
| **Norsk for Beginners** (same creator) | Active | A1–A2 | Bilingual structure | Free | 8/10 | Best for zero-start |
| **NRK / Klar Tale** | Active (NRK public broadcaster; Klar Tale = easy-language news) | A2–C1 | NRK subtitles; Klar Tale simplified text + audio | Free | 8/10 | Authentic input |
| **LingQ Norwegian library** | Active | A1–C1 | Text+audio, pop-up dictionary | ~$12–14/mo | 7/10 | Good toolchain |

*Also considered:* **Norskpodden, Norsklærer Karense (YouTube), Simple Norwegian** — good free supplements. True Krashen-style CI *video* for Norwegian remains thin versus Spanish (no Dreaming-Spanish-scale equivalent).

### Lane D — Output & feedback (no tutor)

| Candidate | Status | What it does | Feedback | Price | Score | Verdict |
|---|---|---|---|---|---|---|
| **Claude (AI, text+voice)** | Active | Conversation partner, error log, "island" rehearsal, prompt-pinned Bokmål | Immediate (verify claims) | Your existing access | **8/10** | **Top pick — your Sunday session** |
| **muntlig.com / MuntligB1** | Active (Lingu-backed) | AI examiner mirroring the four *muntlig* tasks, native Oslo voices, instant feedback | Immediate, exam-shaped | ~499 kr one-time 30-day pass | 8/10 | Best exam-specific reps |
| **HelloTalk / Tandem** | Active | Free exchange with Norwegians | Peer corrections (inline) | Freemium | 6/10 | Useful but flaky (~70% no-reply) |

### Lane E — Exam preparation

| Candidate | Status | What it is | Price | Score | Verdict |
|---|---|---|---|---|---|
| **HK-dir official sample tasks + demo** (prove.hkdir.no; Enovate voxdemo) | Active, official | Real task types across all four skills incl. *muntlig*; assessment schema | **Free** | **10/10** | **Essential** |
| **muntlig.com / norskproven.ai** | Active | AI *muntlig* simulation; norskproven.ai = 295 kr/mo or 495 kr/90-day; muntlig = 499 kr/30-day | Paid | 8/10 | Good supplement |
| **NorskAI (norskai.com)** | Active | 465 tasks A1–B2, writing + speaking, sensor-style assessment | Freemium | 6/10 | Try free tier |

**AI Norskprøven tools — credibility assessment.** muntlig.com is backed by Lingu (an established Oslo school) and is the most credible; norskproven.ai and NorskAI are independent commercial tools that mirror the format reasonably but whose "assessment levels" are unofficial estimates — useful for reps, not for reliable scoring. All three correctly emphasize the real insight: the exam "rewards being able to keep speaking, in the real format, without freezing." Because official questions are never published, all build their question banks from topics reported by past test-takers.

**Bokmål vs Nynorsk / dialect.** Study Bokmål (NoW uses the Oslo-area / Central Eastern Norwegian sound system). Be aware examiners and real Norwegians speak dialects; NoW's own materials warn that dialect divergence in phonology/vocabulary can block comprehension, so deliberately expose yourself to varied speakers (NRK; *Lær norsk nå!*'s dialect episodes). **References:** ordbokene.no (official Bokmål/Nynorsk dictionaries) — free, authoritative.

## SPANISH — second priority, B1–B2 → C1 → DELE C2

**Exam reality.** DELE is the lifetime Instituto Cervantes diploma; C2 is the top. Official past papers ("modelos de examen") for all levels including C2 are free PDFs + audio + answer keys at examenes.cervantes.es ("El Instituto Cervantes pone a disposición… modelos de examen… los audios… y las claves de respuesta"). SIELE is a digital A1–**C1** exam (no C2 certification), useful as a ~€155 diagnostic to confirm you are solidly at C1 before attempting C2 (SIELE Global ≈ €155; individual modules €55–100; validity 5 years vs. DELE's lifetime). Both DELE and SIELE accept all standard regional varieties — you will not be marked down for Latin American vs. Castilian forms if usage is consistent; SIELE's four sponsors (Instituto Cervantes, Salamanca, UNAM/Mexico, UBA/Argentina) exist precisely to reflect pan-Hispanic norms.

### Lane A — Structured course/curriculum (advanced)

| Candidate | Status | Platforms | Level | Feedback | Export | Price | Score | Verdict |
|---|---|---|---|---|---|---|---|---|
| **Kwiziq Spanish** | Active (2026), AI-updated (Kwizbot/StudyPlan) | Web (mobile weak) | A0–**C1 only (no C2)** | Adaptive grammar SRS, error-pinpointing | **No export** (notebook = bookmarks only) | Free tier; Premium ~$16.25/mo (2-yr) to ~$38.99/mo (monthly), by region | **8/10** for B1–C1 | **Top grammar pick to C1** |
| **Instituto Cervantes AVE Global** | Active, official | Web | A1–C1 | Auto + optional tutor | No | Paid | 7/10 | Institutional option |

*Also considered:* textbook series *C de C1/C2*, *Sueña 4*, *Aula Internacional* — solid, but at B2+ you likely don't need a full course; grammar reference + input + exam books is more efficient. **Key caveat: Kwiziq tops out at C1** — use it to solidify B1–C1 grammar, then leave it for the C2 push.

### Lane B — SRS / vocabulary

**Anki** (top; frequency + mined literary/journalistic vocab, full export) with **Clozemaster** (gamified sentence gap-fill, good B2+ consolidation) as runner-up. Reject generic pre-made "Spanish 5000" decks without audio.

### Lane C — Input (advanced, with transcripts)

| Candidate | Status | Level | Transcripts | Price | Score | Verdict |
|---|---|---|---|---|---|---|
| **Radio Ambulante** | Active (Season 15 launched Sep 2025, Season 16 announced; now iHeart/My Cultura) | C1–C2 | **Free Spanish + English on radioambulante.org** | Free | **9/10** | **Top authentic pick** |
| **El Hilo** | Active (weekly Fri, episodes through Aug 2026) | B2–C1 | Free on elhilo.audio | Free | 9/10 | Best for current-affairs Spanish |
| **Dreaming Spanish** | Active; Premium **$8/mo** (Premium Double $12/mo) | Superbeginner–Advanced (top level ≈ B2) | Some subs | $8/mo | 8/10 | Great comprehension; input-only |
| **Hoy Hablamos** | Active (Castilian) | B1–B2 | **Transcripts paywalled** ($9.95/mo or $95/yr) | Freemium | 6/10 | Audio free; skip premium |

*Reading path:* graded readers → journalism (El País, BBC Mundo) → literary fiction; use LingQ or Language Reactor for pop-up support. *Also considered:* **Jiveworld (formerly Lupa)** — paid interactive Radio Ambulante for intermediates; the free web transcripts make it optional at your level.

### Lane D — Output & feedback (no tutor)

**LangCorrect** (free; native speakers correct "sentence by sentence and explain why"; requires reciprocating — top pick) and **Claude** (AI drafting/correction with verification) lead; **Journaly** ($3.50/mo, peer feedback) and **r/WriteStreakES** as runners-up (verify current subreddit activity directly). **HelloTalk/Tandem** for speaking exchange.

### Lane E — Exam preparation

| Candidate | Status | What | Price | Score | Verdict |
|---|---|---|---|---|---|
| **Instituto Cervantes official modelos (incl. C2)** | Active, official | Free past papers + audio + keys (examenes.cervantes.es) | **Free** | **10/10** | **Essential** |
| **El Cronómetro C2** (Edinumen; Tarrés, Pérez Bernal, Isa) | In print | The standard autonomous DELE C2 manual, examiner-written, ~8 models' worth of material + ELEteca | ~$40–55 | **9/10** | **Top C2 book** |
| **Las Claves del nuevo DELE / Preparación al DELE (Edelsa)** | In print | Alternative prep series | ~$35 | 8/10 | Runner-up |
| **SIELE** | Active | Digital A1–C1 diagnostic (~€155; modules €55–100) | Paid | 7/10 | Benchmark C1 before C2 attempt |

## JAPANESE — third priority, N3 maintenance → N2 → N1

**Recommendation up front for a maintenance-mode N3 learner with two 35-min sessions/week.** Do NOT adopt a heavy immersion toolchain. Run a small daily-ish **Anki** deck (mined + N2 vocab) as the backbone, one grammar SRS (**Bunpro** or **Renshuu**) to creep N3→N2, and spend your input hour on **Satori Reader** / **NHK News Web Easy** for graded reading with audio. Maintain speaking/writing via self-recorded monologues + occasional Claude conversation + LangCorrect for writing. This fits the time budget; the full Yomitan/Migaku mining stack is excellent but too time-hungry for maintenance.

### Lane A — Course/grammar

| Candidate | Status | Platforms | Level | Feedback | Export | Price | Score | Verdict |
|---|---|---|---|---|---|---|---|---|
| **Bunpro** | Active (2026) | Web/iOS/Android | N5–N1 grammar SRS | SRS reviews | Some | ~$5/mo | **8/10** | **Top grammar pick** |
| **Renshuu** | Active | Web/iOS/Android | N5–N1 grammar+vocab+kanji | Drills | Limited | Generous free tier | **8/10** | Best free all-rounder |
| **MaruMori** | Active | Web | N5–N1 integrated | SRS | Limited | Subscription | 7/10 | Newer all-in-one |

### Lane B — SRS / vocabulary / kanji

**Anki + Yomitan** (one-click mining; full export; top pick). **WaniKani** for kanji-by-mnemonic if kanji is a measured weak point (subscription). **jpdb.io** if reading a specific media type. *Kitsun* still active but niche.

### Lane C — Input

| Candidate | Status | Level | Transcript/audio | Price | Score | Verdict |
|---|---|---|---|---|---|---|
| **Satori Reader** | Active | N4–N2 | **Graded, human audio, built-in dictionary/grammar notes** | ~$9/mo | **9/10** | **Top graded reading** |
| **NHK News Web Easy** | Active (NHK) | N3–N2 | Furigana + audio | Free | 8/10 | Authentic-lite news |
| **Comprehensible Japanese / YUYU Nihongo Podcast / Nihongo con Teppei** | Active | N5–N2 | Video/podcast; some transcripts | Free/freemium | 8/10 | CI listening |

*Also:* **Todai Easy Japanese** (news reader app), **Language Reactor** (Netflix/YouTube subtitle mining).

### Lane D — Output & feedback

Self-recording + **Claude** conversation + **LangCorrect**/**HelloTalk** for writing correction. No tutor needed for maintenance.

### Lane E — Exam prep (N2/N1)

**Shin Kanzen Master** (comprehensive, exam-level difficulty — the "gold standard," best for the final push and higher scores) is the top pick; **Nihongo Sō-Matome** (gentler, 6-week structured, best as first pass/review) the runner-up. Community consensus: Sō-Matome first, then Shin Kanzen Master ("learn then deepen"). **Try!** and official sample questions on **jlpt.jp** round it out.

## CHINESE — dormant, reactivation note only

Park it now. To reactivate an A1 learner later: **HelloChinese** (best structured beginner app, zero→HSK 3) + **Du Chinese** (graded readers with audio) + **Pleco** (the essential dictionary, with optional SRS add-on) + **Anki HSK decks**. **HSK 3.0 status:** the new three-stage, nine-level standard (国际中文教育中文水平等级标准) was published by the Center for Language Education and Cooperation in **November 2025**, defining **11,000 vocabulary entries, 3,079 recognition characters and 1,200 writing characters across 9 levels (三等九级)**, with cumulative lower-band counts of L1 300 / L2 500 / L3 1,000 / L4 2,000 / L5 3,600 / L6 5,400 words. **First global trial exams ran 31 January 2026; full worldwide implementation was 1 July 2026.** Note the practical nuance: per Chinese Testing International, regular HSK 1–6 sittings continued under HSK 2.0 until the formal cutover was announced (the Jan 31 sitting was a pilot). HSK 3.0 roughly doubles vocabulary versus the old six-level exam and introduces a formal read-vs-handwrite character split, using an "inverted pyramid" that keeps early levels approachable. If reactivating for a certificate, confirm which version your test center administers; build any *new* study plan on HSK 3.0.

---

# CROSS-CUTTING QUESTIONS

**Single SRS for all three languages?** **Yes — use Anki.** It handles Norwegian, Spanish, and Japanese (with Yomitan for JP mining), is free (except the $25 iOS app), works offline on every platform, and has the best data export of any tool here (.apkg/.txt/.csv). A single platform is worth it for the shared habit, unified review time, and one data store. The only "best-of-breed" layers worth adding: **Bunpro/Renshuu** for Japanese grammar sequencing and **Kwiziq** for Spanish grammar — but keep raw *vocabulary* in Anki.

**Multi-language platforms — genuinely good for Norwegian, or padding?**
- **LingQ** — *genuinely good* for Norwegian (real library of text+audio incl. *Lær norsk nå!*, pop-up dictionary, auto-SRS); worth it if you live in its reading workflow. ~$12–14/mo.
- **Pimsleur Norwegian** — *good but narrow*: research-based audio, gets you speaking basics fast, but only ~1 level of Norwegian, outdated scenarios, expensive. A short on-ramp, not a program.
- **Babbel Norwegian** — *good beginner value*, in-house-built, but finite; outgrow it.
- **Michel Thomas Norwegian** — decent audio-only grammar-intuition intro; limited depth.
- **Glossika Norwegian** — mass-sentence audio drilling (if available for NO); useful for reps, pricey.
- **Speakly, Mondly, Ling, Drops** — *mostly padding* for serious Norwegian; thin content, weak progression.
- **Language Reactor** — great *tool* (subtitle mining) but content-agnostic; useful for any subtitled-video language.
- **Clozemaster** — good B1+ consolidation across languages, secondary.

**Free language-exchange platforms (2026).** **HelloTalk** (largest community, best inline-correction tool, Moments feed) and **Tandem** (stricter moderation, more serious/older users, better for scheduled calls) are the two viable options. Both share a ~70% initial no-reply/flake rate; safety caveats apply (HelloTalk gets more spam/romance-pivot messages — hide personal details, block early). For Norwegian specifically the pool is smaller than for major languages; set a fixed weekly time with a committed partner to beat the flake rate. Verdict: a useful *free* speaking supplement, not a reliable core — your AI sessions are more dependable.

**Data portability (who lets you export).** **Anki** — full export, best-in-class. **LingQ** — partial (vocabulary export). **Kwiziq** — no export (notebook = bookmarks only; account deletion by email). **Bunpro/Renshuu** — limited. **Dreaming Spanish** — logs input hours and lets you record outside input on the progress page, but exportable data is limited. **Recommendation:** keep your canonical personal tracker as a spreadsheet you own, with Anki as the vocabulary system of record; treat everything else as a consumable service you can leave without losing your data.

---

# RECOMMENDED "ONE RESOURCE PER LANE" STACK (+ runner-up)

**Norwegian**
- A Course: **NTNU Norwegian on the Web (NoW1→NoW2)** · runner-up LearnNoW
- B SRS: **Anki** (frequency deck + mined) · runner-up LingQ
- C Input: **Lær norsk nå!** (+ Norsk for Beginners at start) · runner-up NRK/Klar Tale
- D Output: **Claude** (AI conversation + error log) · runner-up muntlig.com
- E Exam: **HK-dir official sample tasks + demo** · runner-up muntlig.com

**Spanish**
- A Course/grammar: **Kwiziq** (to C1) · runner-up Instituto Cervantes AVE Global
- B SRS: **Anki** · runner-up Clozemaster
- C Input: **Radio Ambulante** (+ El Hilo) · runner-up Dreaming Spanish
- D Output: **LangCorrect** (+ Claude) · runner-up Journaly / r/WriteStreakES
- E Exam: **Instituto Cervantes modelos + El Cronómetro C2** · runner-up Las Claves del nuevo DELE; SIELE to benchmark C1

**Japanese**
- A Grammar: **Bunpro** · runner-up Renshuu
- B SRS/kanji: **Anki + Yomitan** · runner-up WaniKani
- C Input: **Satori Reader** · runner-up NHK News Web Easy
- D Output: **Self-recording + Claude** · runner-up LangCorrect/HelloTalk
- E Exam: **Shin Kanzen Master** · runner-up Nihongo Sō-Matome

---

# SUGGESTED TWO-WEEK TRIAL PLAN (with keep-or-kill criteria)

Map to your fixed schedule: **Mon–Fri 1 hr morning** (30 min Norwegian daily; second 30 min = Spanish Mon/Wed/Fri, Japanese Tue/Thu); **optional evening hour = input only**; **Sunday = Norwegian speaking with Claude + weekly review**.

**Week 1 — install and baseline**
- Norwegian: NoW1 Ch.1–2 (15 min) + Anki 10 new/day (15 min). Evening input: *Norsk for Beginners* with transcript. Sunday: first Claude Norwegian session — pin "respond only in Bokmål, correct my errors, keep a running error list," and rehearse the introduction task.
- Spanish (M/W/F): Kwiziq placement test + StudyPlan; evening input Radio Ambulante with transcript.
- Japanese (T/Th): Bunpro or Renshuu placement; one Satori Reader episode.
- Set up your owned spreadsheet tracker (sessions, input minutes, recurring errors).

**Week 2 — exam-format and toolchain**
- Norwegian: continue NoW; Sunday, run a full *muntlig* mock with Claude (all four tasks) AND one free muntlig.com/NorskAI session to compare; try the HK-dir demo test.
- Spanish: 3 Kwiziq lessons + 1 LangCorrect journal entry; attempt one section of an Instituto Cervantes C2 modelo to gauge the gap.
- Japanese: 2 grammar-SRS sessions + confirm Anki+Yomitan mining works on one article.

**Keep-or-kill criteria (for mixed-evidence resources):**
- **Kwiziq:** *Keep* if after 2 weeks its StudyPlan surfaces genuine B2/C1 gaps you can't self-diagnose; *kill* if it feels like A2/B1 review — switch to free grammar reference + El Cronómetro. (It stops at C1, so plan to leave it before the C2 push.)
- **muntlig.com / norskproven.ai (paid):** *Buy the short pass only when your exam is <4 weeks out* and you need format reps; *skip* if Claude + HK-dir samples already give enough realistic practice (they usually do for A2).
- **Dreaming Spanish Premium ($8):** *Keep* if you're logging ≥2–3 input hours/week and enjoying it; *kill* if Radio Ambulante/El Hilo (free) already fill your listening hour — they are more level-appropriate at B2+.
- **LingQ ($12–14/mo):** *Keep* only if you consolidate reading for ≥2 languages inside it weekly; *kill* if Anki + free transcripts cover you (they do for most).
- **HelloTalk/Tandem:** *Keep* if you land ≥1 reliable weekly partner within 2 weeks; *demote to occasional* if you hit the typical flake wall — lean on AI instead.
- **WaniKani (JP):** *Keep* only if kanji recognition is a measured weak point; *kill* if your N3 kanji base is holding — don't add review load in maintenance mode.
- **jpdb/Migaku (JP):** *Kill by default* for a maintenance learner — revisit only if you shift Japanese from maintenance to active growth.

---

# CAVEATS
- **Verify official exam rules yourself before relying on them.** The Norskprøven-as-sole-requirement change (1 Sep 2025), HK-dir formats, DELE/SIELE details, and HSK 3.0 cutover are current as of research on 29 Aug 2026 but change; confirm on hkdir.no/UDI, examenes.cervantes.es, jlpt.jp, and CTI.
- **Prices localize and change.** Kwiziq (~$16–39/mo by plan/region), Dreaming Spanish ($8/$12), muntlig.com (~499 kr), norskproven.ai (295 kr/mo), SIELE (~€155), Bunpro (~$5), Satori (~$9), LingQ (~$12–14), Hoy Hablamos ($9.95/mo), Journaly ($3.50/mo) were captured March–Aug 2026 from product/third-party pages; check live pages before buying.
- **AI feedback is fallible.** LLMs (incl. Claude) produce fluent-but-wrong grammar corrections, can hallucinate "rules," and drift out of the target language/register. Cross-check against ordbokene.no, a grammar reference, or a prep book; don't treat AI "level assessments" as official.
- **Community sources are consensus, not evidence.** Refold, The Moe Way, subreddit wikis, and polyglot blogs reflect experienced-learner convergence and are labeled as such; where they conflict with meta-analyses (e.g., "input is sufficient, never study grammar"), the research view is weighted higher.
- **Some product-review sources are affiliate/SEO** (app "best-of" listicles; vendor blogs like LingQ/Migaku/immit reviewing rivals). These were used only as leads; status/pricing/feature claims were confirmed against primary/official sources where possible. A few pricing captures remain single-sourced and are flagged as such. The Hoy Hablamos transcript-cost claim in particular was resolved in favor of the official site ($9.95/mo, transcripts paywalled) over a third-party claim that they were free.
- **Norwegian CI gap:** unlike Spanish, Norwegian lacks a large Dreaming-Spanish-scale comprehensible-input video library; *Lær norsk nå!* + NRK + Klar Tale are the best available but require more self-curation.
- **Kwiziq and SIELE both stop at C1** — neither can take you to, or certify, DELE C2; only the DELE C2 exam and dedicated C2 materials (El Cronómetro C2, official modelos, heavy authentic input, and native writing correction) close that final stretch.