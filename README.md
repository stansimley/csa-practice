# CSA Practice

Independent, mobile-first ServiceNow CSA study PWA. 300 original questions with explanations and official documentation references. Not affiliated with ServiceNow and not an exam dump.

## Run and deploy
Serve this directory with a static HTTP server (for example `python -m http.server 8000`). In GitHub Settings → Pages, choose Deploy from a branch, main, / (root). All application paths are relative for repository-subpath hosting.

## Architecture
`index.html` and `styles.css` provide the responsive interface. `app.js` manages navigation, localStorage persistence, practice, exam timers, bookmarks, mistakes and history. `core.mjs` contains randomisation, weighted selection and exact-match scoring. `questions.json` is the independent question bank. `sw.js` precaches the app for offline operation. Icons and manifest support home-screen installation.

## Question schema
Each entry has `id`, numeric `domain` (1–6), `kind` (scenario, terminology, concept), `prompt`, `options` (text, correct boolean, explanation), and `sources` (official URLs). Preserve IDs when editing. Multiple-select scoring requires all correct options and no extra options.

## Blueprint
January 2026 official CSA blueprint: 60 questions, 90 minutes; weights 7%, 10%, 20%, 20%, 30%, 13%. Mock exam integer allocation is 4, 6, 12, 12, 18, 8. Bank allocation is 21, 30, 60, 60, 90, 39. The official passing score is not public. Difficulty is an approximation, not validated against live exam items.

https://learning.servicenow.com/kb?id=kb_article_view&sysparm_article=KB0011554

## Updates and privacy
Bump CACHE in sw.js whenever cached assets change. A waiting worker is offered after an active session; keep question IDs stable. No backend, analytics, accounts or external AI. Progress stays on the device and is lost if browser data is cleared. An exam deadline continues while the app is closed. Install through Safari → Share → Add to Home Screen; load once online before offline use.
