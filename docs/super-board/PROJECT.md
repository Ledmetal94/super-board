# PROJECT — super-board

Drafted by onboard on 2026-10-29 from README, VERSION and the tree. Edit freely; the board reads
this file as context, never as config.

## What it is

super-board v3.1.2 — a GitHub-Project-driven autonomous pipeline shipped as an installable pack of
eight skills, nine commands and six guard hooks. Add tickets to a Project board, start a run, get
merged PRs with evidence. Live site: erictechpro.github.io/super-board.

## Shape

| Area | Where |
|---|---|
| Skills (8) | `skills/` — user-typed: `super-board`, `super-collect`, `ui-refine-loop`, `visual`, `git-sync` · board-run lanes: `super-build`, `super-qa`, `super-review` |
| Dispatcher scripts | `scripts/` → installed as `.claude/bin/super-board-*` |
| Wave engine | `workflows/super-board-wave.js`, `workflows/ui-refine-loop.js` |
| Guards | `hooks/guard-*.py`, `hooks/cleanup-wt.py` |
| Installer | `install.sh`, `get.sh` (copies into `.agents/`, links each host folder) |
| Map pages | `diagrams/` — registry `diagrams/_shared/maps.json`, synced Explore cards |
| Evals | `evals/` — skill eval fixtures and runner |
| Offline suite | `tests/run-safety.sh` |

## How this repo is worked

- The pack builds and markets itself: fixes and features arrive as cards on the Superboard project
  board and are drained by the lane agents this repo ships.
- Everything an agent must know is in `AGENTS.md`; `CLAUDE.md` is the `@AGENTS.md` pointer.
- Ticket format: `docs/agents/issue-tracker.md`.
- Writing standard for commits, PR bodies, tickets and comments:
  `skills/super-board/references/writing-standard.md` — README tables are generated from skill
  frontmatter by `scripts/super-board-readme-sync.py`, never hand-edited.

## Run config

`.claude/super-board/configs/superboard.json` — board `Ledmetal94/projects/1`, base branch `main`
(pages.yml deploys it), every merge waits for a human, verify command `bash tests/run-safety.sh`.
