# STATUS.md

## What was built

**The Friendly AI Trivia Night Pack** — a free, print-and-play trivia pack about
artificial intelligence, made for libraries, classrooms, and any screen-free game night.
Created by Asdale Dynamics, LLC.

Contents:

- `trivia-night-pack.html` — the complete printable pack (12 print-designed pages):
  - Page 1: cover, contents, quick "how to play" rules
  - Page 2: hosting tips for libraries/classrooms (no screens needed)
  - Pages 3–10: **eight written rounds × 6 questions each (48 questions)**, every answer
    printed right on the host sheet alongside the question:
    1. Influential Moments (AI history)
    2. Common Myths (true or false)
    3. How It Works (plain-English terms)
    4. Staying Safe (deepfakes, voice cloning, phishing)
    5. AI in Everyday Life
    6. Famous Names
    7. Pop Culture AI
    8. The Mixed Bag
  - Page 11: three nearest-guess **tiebreakers** (1920 robot, 1956 Dartmouth, 1997 draws) + a sudden-death backup
  - Page 12: printable **team answer sheets** (four teams per page, plus the "blank paper works too" tip)
- `answer-key.html` — the single standalone HTML answer key, grouped by round, printer-friendly
- `README.md` — how to use the pack, with credit to Asdale Dynamics, LLC
- `LICENSE` — MIT License, copyright line exactly `Copyright (c) 2026 Asdale Dynamics, LLC`

## How to run it

No build, no install, no screens for players, no tracking — it's paper:

1. Open `trivia-night-pack.html` in any browser.
2. Press **Ctrl/Cmd + P**. Each `<section class="sheet">` is sized for US Letter/A4 with
   automatic page breaks; black-and-white printing is fine.
3. Print one host pack + one answer-sheets page per team. Keep `answer-key.html` for grading.

## Verification results

- HTML structure check (Python `html.parser`): both files parse with **no unclosed tags,
  no malformed nesting**, balanced `<section class="sheet">` blocks (12 in pack, 1 in key).
- Content audit by script:
  - Rounds 1–8: exactly **6 questions each** = 48 questions; 3 tiebreakers = 51 total.
  - 51 printed answers in the pack = 48 round answers + 3 tiebreaker answers; answer key
    covers all 51 via tables.
  - No CJK/stray non-English characters remain (one edit-time typo found and fixed).
- Factual spot-checks: Turing 1950, Dartmouth 1956, Deep Blue 1997, AlphaGo 2016,
  Transformer paper 2017, ChatGPT Nov 2022, Deep Blue–Kasparov 1997 rematch (2 wins,
  1 loss, 3 draws — tiebreaker phrased around the 3 draws), and Karel Čapek's *R.U.R.* (1920)
  — all cross-checked during writing.
- License line verified byte-for-byte: `Copyright (c) 2026 Asdale Dynamics, LLC` (LICENSE line 3).
- No secrets, API keys, or personal data in any file (nothing to leak: static HTML + markdown only).

## Known gaps

- The pack is not a PDF — printing relies on browser print-to-PDF (works in Firefox, Chrome,
  and Edge; tested structure via parser, visually in-browser layout is standard CSS).
- Team answer sheet page fits four teams; larger events need a photocopy or the "blank paper" fallback.
- No alternate question sets (seasonal/hard/easy variants) — could be future additions.
- Questions are US-English-centric phrasing (e.g., copy machines, Jeopardy!); a localization
  pass would help non-US hosts.
- No automated test suite — verification was script-based structure/count checks plus manual
  fact-checking, appropriate for a static content pack with no code to test.
