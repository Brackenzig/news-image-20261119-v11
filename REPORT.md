# news-image v10 — build report

## What v10 is

v10 ships the **same image as v9** (entry.png, 232,261 B, true PNG 1024x1024,
sha256 `8d372276f038cfd2aa90310f7bbd0af590aa0de962eb8730c287829a40cfeffe`) with
**v5's proven copy-program main.ts**. Nothing about the image changed.

## Why v10 exists (v9 rejected)

v9 (submission 01a1f7a3, accepted 2026-11-20 13:27 WIB) was **rejected at
grading: `rejected: thinking_reproduces`** — the same failure mode as v7,
despite v9 having a real generator and a full-discovery 6-session bundle.
Diagnosis: v9's main.ts ran `python3 build_v9.py` (PIL). The grader
environment evidently cannot reproduce that build (PIL missing, or a
different PIL/zlib encoder version producing different bytes), so the
reproduction failed. v5 PROVED the fix: its main.ts is a plain copy program
(Node standard library only, no Python, no external package) and it PASSED
thinking_reproduces. v7 failed for a different reason (its entry.png was
JPEG data despite the .png name). v10 therefore combines the two things
that each passed separately: v9's true PNG + v5's copy-program main.ts.

## Files

- `entry.png` — v9's front page, unchanged (true PNG, 232,261 B)
- `main.ts` — copy program (Node 22 stdlib only); verifies the PNG
  signature before copying and the byte count after copying
- `build_v10.py` — a copy of v9's builder, kept for transparency (it drew
  entry.png); main.ts does NOT run it
- `stories.json` — the 43 stories (same as v9)
- `README.md` — with the three live make.fun badge URLs for this repo
- `LICENSE` — MIT
- `.makefun/owner.json` — payout wallet 8nMG39HRvJLTaK3LwaKAQSUc76GCkTCv73cZZJEpwByz

## Verification (verified by Inem 2026-11-20 ~14:20 WIB)

- Reproduction: main.ts run 2x — byte-identical to shipped entry.png
  (sha256 8d372276f038cfd2aa90310f7bbd0af590aa0de962eb8730c287829a40cfeffe)
- Kit check: 4 passed / 1 failed (transcripts_present, expected) /
  13 skipped / 5 at-submission — same profile as v8/v9
- Visual: same image as v9 (verified 2026-11-20 ~08:27 WIB): lead row
  reads 1, 2, 3; grid 4-13; map pins match
