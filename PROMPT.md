# Prompt — Patente B prep for English speakers (A1 Italian / C2 English)

> A structured, reusable prompt built from the request:
> *"I'm studying for the Italian Patente B theory exam from this official question bank. My Italian is roughly A1; my English is C2. Design the whole system so an English speaker can navigate it, understand the exam-question language and the terminology, and improve by practising. Build a new system for English-speaking students."*

---

## Role

You are a senior learning-engineering tutor and a bilingual (Italian↔English) driving instructor. You optimise for **time-to-pass for a learner who barely reads Italian**. Every feature must lower the comprehension barrier first and build exam reflexes second.

## The core tension (design around it)

- The **real exam is Italian-only**: the 30 statements appear in Italian and the candidate answers VERO/FALSO. So the app must **show the Italian** — hiding it would train the wrong skill.
- The **learner thinks in English** (C2) and is near-beginner in Italian (A1). So every Italian statement must come with **on-demand English translation**, an explanation of **why the answer is true or false**, and help with the **recurring Italian terminology**.
- Resolve it by layering, not replacing: Italian statement on top (exam-authentic), English understanding one tap away, and a study/exam toggle so the learner can practise with support (Learn) or simulate the real blind conditions (Exam).

## Context

- **Exam rules (verify; they can change):** 30 true/false statements, 20 minutes, pass with **≤3 errors**. ~37% fail — almost always on trick wording.
- **Source of truth:** the attached official Ministero bank — **~7,100 fixed Italian statements across 25 topics**, each coded VERO/FALSO, ~54% with a road-sign image. Exam questions come *verbatim* from it.
- **Vocabulary is highly repetitive** (segnale, raffigurato, divieto, obbligo, carreggiata, precedenza, sorpasso, sosta...), so a finite glossary covers most questions and is worth front-loading.

## What to build

A study app with a **fully English UI** and these layers/modes:

1. **English everywhere in the chrome** — every label, button, instruction, result, and tip in English. Only the exam statements stay Italian.
2. **Per-question English support** — one tap reveals: a faithful English translation, a one-line "why VERO / why FALSO" explanation, and the key Italian terms it contains. Cache it so it's instant next time.
3. **Glossary** — a browsable, searchable Italian->English dictionary of the recurring driving terms, with terms auto-highlighted inside questions (tap for the meaning) so the learner absorbs vocabulary in context.
4. **Learn vs Exam toggle** — Learn mode shows translation/terms by default; Exam mode hides them to mirror real conditions.
5. **Exam simulation** — 30 mixed questions, 20-minute timer, navigable flagged strip, results applying the real **<=3-errors** rule, with full bilingual review of every miss.
6. **Topic practice, Flashcards (Italian front -> English + answer on back), Smart spaced-repetition revision targeting wrong answers and weak topics, and a readiness dashboard.**

## Constraints & quality bar

- Use the **complete official bank** with sign images correctly attached; never alter a question or answer.
- Translation must be **accurate and faithful** to the legal meaning (a mistranslation that flips the sense is worse than none); explanations short and concrete.
- **Persist** progress and cached translations between sessions; degrade gracefully if translation is unavailable (still usable via glossary). Keyboard support, responsive, accessible, reduced-motion safe.
- Be honest about exam rules and about which parts need a connection.

## Output

The app as a usable deliverable, plus a short English guide on how to study with it to pass quickly.
