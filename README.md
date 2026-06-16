# 🚗 Patente B — English Study Lab

**Live app → [ejazfahil.github.io/patenteB_en_feil](https://ejazfahil.github.io/patenteB_en_feil)**

An unofficial study tool for the Italian **Patente B** (driving licence) theory exam, designed for **English speakers with A1 Italian**.

---

## What this is

The Italian Patente B exam is 30 true/false statements **in Italian**, 20 minutes, and you must score ≤ 3 errors to pass. About 37% of candidates fail — almost always on tricky wording.

This app solves the core tension:

- **The real exam is Italian-only** → the app always shows the Italian statement
- **You think in English (C2)** → every statement has an **"English translation & Why"** dropdown

---

## English translations — how they work

Each question has a collapsed **"English translation & Why"** dropdown. When opened it shows the best available source, in this order:

1. **Pre-baked pack** (`translations.json`) — loads instantly, fully offline. *This is what makes the deployed site show translations without any connection.*
2. **Live translation** — only when the app is opened inside Claude (claude.ai), where the translator runs. Results are cached.
3. **Word-by-word breakdown** — from the built-in 360-term glossary. Always works, no connection.

The official VERO/FALSO answer is embedded data and **never** depends on the translation.

### Building the translation pack (one time)

A static site (GitHub Pages) has no translator, so the full English sentences must be baked into a file:

1. Open the app **inside Claude** (claude.ai) so the translator is reachable.
2. Go to **Tools → Build / resume pack**. It batch-translates all ~7,100 questions (resumable; progress is saved).
3. Click **Download translations.json**.
4. Commit that file to the repo root (next to `index.html`) and push. The deployed site now shows full English translations instantly, offline.

Until the pack exists, the deployed site still shows the word-by-word breakdown + the correct answer for every question.

---

## Features

| Feature | What it does |
|---|---|
| 📚 **Topic Practice** | Drill all ~7,100 questions by one of 25 official categories |
| 🎴 **Flashcards** | Italian front → flip for English + VERO/FALSO |
| 🧠 **Smart Review** | Spaced-repetition targeting your weak spots |
| 🏆 **Mock Exam** | 30 questions · 20-min timer · real ≤3-errors rule · bilingual review |
| 📖 **Glossary** | Searchable Italian→English driving vocabulary (360 terms) |
| 🔍 **Search** | Find any question and its VERO/FALSO |
| 🛠 **Tools** | Build & export the translation pack |
| 📊 **Dashboard** | Readiness gauge + accuracy by topic |

---

## How to study (fast-track)

1. **Glossary first** — learn the recurring Italian terms (`segnale`, `divieto`, `obbligo`, `sorpasso`, `sosta`, `corsia`…). They unlock most questions.
2. **Topic Practice** with **Auto-open English ON** — read the Italian, then the translation + why.
3. **Mock Exams** (blind, Italian-only) — review every miss in English afterwards.
4. **Smart Review** daily — it resurfaces your weakest questions automatically.

---

## Exam rules (always verify with the Motorizzazione)

30 statements · mark each VERO or FALSO · 20 minutes · **≤ 3 errors = PASS**.

---

## Tech

Single self-contained `index.html` — no server, no install, works offline. All ~7,100 official Ministry questions are embedded with their road-sign images. Progress and cached translations persist locally (`window.storage` when in Claude, `localStorage` otherwise). Deployed via GitHub Pages (`.github/workflows/deploy.yml`).

*Unofficial study tool. Not affiliated with the Ministero delle Infrastrutture e dei Trasporti.*
