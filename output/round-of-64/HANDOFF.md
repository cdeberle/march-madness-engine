# Round of 64 — Session Handoff

## How to Resume

Start a new Claude Code session in this project directory. Say:

> "Resume the round-of-64 analysis from the checkpoint."

Then Claude will:
1. Read `CLAUDE.md` for rules (max 4 agents, sonnet, foreground only)
2. Read `agents/orchestrator.md` for the full process
3. Read `output/round-of-64/checkpoint.json` for progress state
4. Read `output/round-of-64/picks.json` and `analysis.md` for completed results
5. Resume from the `next_matchup` in `checkpoint.json`, appending to both files

## Current State

- **Games completed:** 13 of 32 (Games 1-13)
- **Regions completed:** East (8/8)
- **Regions in progress:** South (5/8 done)
- **Next game:** Game 14 — (3) Illinois vs (14) Penn (South)

## Upsets Picked So Far

| Game | Matchup | Pick | Reason |
|------|---------|------|--------|
| 5 | (6) Louisville vs (11) South Florida | South Florida | Recency override — Mikel Brown Jr. OUT (back injury) |
| 10 | (8) Clemson vs (9) Iowa | Iowa | Stirtz best player on floor + Clemson lost 2 to ACL tears |

## Close Calls / Upset Alerts

| Game | Matchup | Pick | Confidence | Why It's Close |
|------|---------|------|------------|----------------|
| 13 | (6) UNC vs (11) VCU | UNC | 59% | Wilson OUT (19.8 PPG). VCU 16-of-17 hot streak. Recency agent picked VCU. |
| 11 | (5) Vanderbilt vs (12) McNeese | Vanderbilt | 68% | McNeese #1 forced TO rate nationally, beat Clemson as 12-seed in 2025 |
| 7 | (7) UCLA vs (10) UCF | UCLA | 65% | 7-vs-10 is ~40% upset rate. UCF has wins over Kansas, Texas Tech |
| 2 | (8) Ohio State vs (9) TCU | Ohio State | 61% | True coin flip. 8-vs-9 historically favors 9-seeds |

## Key Learnings for Next Session

1. **Agent prompt length matters.** Tighter prompts with "MAX 5-8 web searches" reduced agent time from 5 min to ~1 min each.
2. **Blocked sources are documented in each agent file.** KenPom, Barttorvik, The Athletic, Warren Nolan are all blocked. EvanMiya may be paywalled — agents should fall back to ESPN BPI + Sports Reference.
3. **Log every game immediately.** Append to `picks.json`, `analysis.md`, and update `checkpoint.json` after every synthesis. This is the critical safeguard against token exhaustion.
4. **8-vs-9 and 7-vs-10 games are near toss-ups.** Don't expect high confidence from agents on these — 55-65% is appropriate.
5. **Recency overrides are real.** The Louisville/USF call was driven by a confirmed injury (Brown OUT). Always check for material roster changes before defaulting to statistical picks.
6. **~3% per game is the actual cost** with tighter prompts (down from ~5% initially). Budget ~13-15 games per session.
7. **Agent prompt template is stable.** Use the compact format from Games 11+ (role, search cap, blocked sources, matchup, JSON-only output). Don't revert to the verbose Game 1-3 format.
8. **Debate protocol edge cases encountered:** Game 13 (UNC vs VCU) — recency agent picked VCU due to Wilson OUT, but both data-tier agents still picked UNC, so no override was applied. The rule is: recency override only triggers when the roster change would flip the statistical baseline, AND data agents split or agree with the override.

## Files to Read on Resume

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Sub-agent rules (max 4, sonnet, foreground) |
| `agents/orchestrator.md` | Full analysis process |
| `agents/schema.md` | JSON output format |
| `output/round-of-64/checkpoint.json` | Progress tracker with all 32 games listed |
| `output/round-of-64/picks.json` | Completed picks (append new ones) |
| `output/round-of-64/analysis.md` | Completed analysis (append new ones) |

## Session Budget

Each game consumes ~3% of session context (with MAX 5-8 search cap on agents). A single session can handle ~13-15 games. Plan for ~2 more sessions to finish the remaining 19 games.

## Remaining Matchups (19 games)

### South (3 remaining)
- Game 14: (3) Illinois vs (14) Penn
- Game 15: (7) Saint Mary's vs (10) Texas A&M
- Game 16: (2) Houston vs (15) Idaho

### West (8 remaining)
- Game 17: (1) Arizona vs (16) Long Island
- Game 18: (8) Villanova vs (9) Utah State
- Game 19: (5) Wisconsin vs (12) High Point
- Game 20: (4) Arkansas vs (13) Hawai'i
- Game 21: (6) BYU vs (11) Texas
- Game 22: (3) Gonzaga vs (14) Kennesaw State
- Game 23: (7) Miami vs (10) Missouri
- Game 24: (2) Purdue vs (15) Queens

### Midwest (8 remaining)
- Game 25: (1) Michigan vs (16) Howard
- Game 26: (8) Georgia vs (9) Saint Louis
- Game 27: (5) Texas Tech vs (12) Akron
- Game 28: (4) Alabama vs (13) Hofstra
- Game 29: (6) Tennessee vs (11) M-OH/SMU
- Game 30: (3) Virginia vs (14) Wright State
- Game 31: (7) Kentucky vs (10) Santa Clara
- Game 32: (2) Iowa State vs (15) Tennessee State
