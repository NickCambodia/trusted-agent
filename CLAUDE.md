# Trusted Agent

Professional training for real estate agents in Cambodia, for any agency. Free and public. Style: premium, pictures over
text, one idea per card, natural voices, a journey home screen (a tower: each level is a band of floors, the rooftop is
"Certified Agent"). Private context: `CLAUDE.local.md` (git-ignored).

## Principles
- Neutral: no company, person, project or developer is promoted. "Your manager" and "an independent lawyer" stand for
  the people an agent should ask; projects are described ("a completed, managed BKK1 condo").
- English first, then Khmer (reviewed by a native speaker before shipping).

## What's here
- `index.html`: the whole app (HTML + CSS + JS). Content in `const TRAINING = {...}` (JSON): `weeks` (level names) and
  `lessons`. Lesson shape, cards, decisions, pictures: .
- Levels now: Foundation (the professional agent, the Phnom Penh market with the REAKH 2026 case study, property law,
  client types), Professional Presence (6), Tough Calls (6 decisions), Client & Advisory Skills (5), Advanced Advisory (5),
  Performance (5, ends with Graduation). 31 steps. `RANKS` 7 (… Certified Agent), `ALTS` floors per level.
- Market facts: Realestate.com.kh "Cambodia Condo Investment Guide 2026" (credited as public data in the lessons).
  Foreign ownership: not in a foreigner's own name for ground floor/land; legal routes exist (licensed trust, company at
  least 51% Cambodian, with a lawyer); never a nominee.
- `audio/` + `audio/manifest.js`: Kokoro clips (coach af_heart, client am_fenrir, model am_michael 0.92, manager
  bm_george for `who:"Manager"` turns). `"~/Desktop/Speak Like A Leader/tools/.venv/bin/python" tools/make_voice.py`
  (only changed lines regenerate; `speakable()` reads money/percent/years naturally).
- `sw.js`: offline copy, caches `ta-*`. Storage: localStorage `trusted-agent-v1`, IndexedDB `trusted-agent`.
- Icons: `icons/icon-{180,192,512}.png` (a brass house with a check on deep ink).

## Steps and voice (2026-10-02)
- A section's numbered steps (`flow`) are read one at a time: the coach introduces the section, then each step lights up
  (`fl-now`) while its clip `c-at{i}-s{k}-f{j}` plays ("Step one: …"); unread steps wait faded (`fl-seq`); tap a step to
  hear it again (`ls-flow`). Coach off = all steps shown.
- The voice never reads markup: `flowing()` in make_voice.py turns pause dots into commas/full stops so each line is one
  natural sentence; `speakable()` says an abbreviation once ("Capital Gains Tax (CGT)" → the name) and Realestate.com.kh
  as "Real Estate dot com dot K H".

## Writing rules
No dashes in content; sentence case; abbreviations written out on first use; numbers spoken naturally; nothing
company-specific. Verify any market number against a source before adding it.

## Plan
- Phase 1 (done 2026-10-01): neutral engine + 31 lessons from Agent Training.
- Phase 2: new lessons: leads and first contact, listings and sellers, rentals and landlords, closing and after-sales,
  personal brand and digital channels, fraud and money-laundering red flags; final assessment + shareable certificate.
- Phase 3: Khmer (reviewed by a native speaker).
- Later (needs a server): manager dashboard, paid licences.
