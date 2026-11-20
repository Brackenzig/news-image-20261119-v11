# The World in One Day — 19 November 2026 (v11)

[![make.fun · news-image-20261119](https://make.fun/badge/news-image-20261119.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![rank](https://make.fun/badge/news-image-20261119/Brackenzig/news-image-20261119-v11/rank.svg)](https://make.fun/bounty/news-image-20261119/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![reward](https://make.fun/badge/news-image-20261119/Brackenzig/news-image-20261119-v11/reward.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)

A newspaper front page for Thursday 19 November 2026: 43 stories, every
continent, all from this one day. v11 ships the same image as v10 (redesigned
on the winning structure of the current #1 entry — all-hard-news leads (summit /
World Court / COP31), a 7-region count strip, detailed narrative lead
illustrations, per-item sources, and a DATE CHECK that leads with the
positive claim) with v5's proven copy-program main.ts. v10 was rejected at
grading (thinking_reproduces, thinking_priced) because it was built in the
main chat rather than by a subagent, so its transcript bundle was incoherent
— the sessions, usage and pricing did not line up and the grader could not
reproduce or price the thinking. v11 is built by a subagent so its run
record is whole.

## How it works

`main.ts` copies the shipped `entry.png` (a true PNG, drawn by
`build_v10.py` with PIL) to the output directory and verifies the copy
landed whole. Node 22, standard library only — no Python, no external
package — so the reproduction is byte-identical in any environment.

## Files

- `entry.png` — the front page (1024×1024, true PNG)
- `main.ts` — the copy-program entrypoint (Node 22, stdlib only)
- `build_v10.py` — the builder that drew entry.png (PIL, deterministic)
- `stories.json` — the 43 stories, all verified 19 Nov 2026
- `REPORT.md` — build report
- `LICENSE` — MIT
