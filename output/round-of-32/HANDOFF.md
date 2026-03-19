# Round of 32 — Session 2 Handoff

## Current Progress

**10 of 16 games completed.** East done. South done. West 2 of 4 done.

## Completed Picks

| Game | Region | Matchup | Winner | Confidence | Upset? | Consensus |
|------|--------|---------|--------|-----------|--------|-----------|
| 1 | East | Duke (1) vs Ohio State (8) | **Duke** | 84% | No | Unanimous |
| 2 | East | St. John's (5) vs Kansas (4) | **St. John's** | 60% | Yes | Unanimous |
| 3 | East | South Florida (11) vs Michigan State (3) | **Michigan State** | 71% | No | Unanimous |
| 4 | East | UCLA (7) vs UConn (2) | **UConn** | 68% | No | Split |
| 5 | South | Florida (1) vs Iowa (9) | **Florida** | 83% | No | Unanimous |
| 6 | South | Vanderbilt (5) vs Nebraska (4) | **Vanderbilt** | 59% | Yes | Unanimous |
| 7 | South | North Carolina (6) vs Illinois (3) | **Illinois** | 76% | No | Unanimous |
| 8 | South | Saint Mary's (7) vs Houston (2) | **Houston** | 71% | No | Unanimous |
| 9 | West | Arizona (1) vs Utah State (9) | **Arizona** | 79% | No | Unanimous |
| 10 | West | Wisconsin (5) vs Arkansas (4) | **Arkansas** | 57% | No | Split |

## Sweet 16 So Far

- **East**: Duke (1) vs St. John's (5), Michigan State (3) vs UConn (2)
- **South**: Florida (1) vs Vanderbilt (5), Illinois (3) vs Houston (2)
- **West** (partial): Arizona (1) vs Arkansas (4), Game 11 winner vs Game 12 winner

## Upsets Picked (2)

1. **St. John's (5) over Kansas (4)** — BPI #16 vs #21. Pitino pressure vs shallow KU bench. Kansas 5 of last 8 losses.
2. **Vanderbilt (5) over Nebraska (4)** — BPI #14, AdjEM #12 vs Nebraska #18/#15. ORtg gap decisive. Nebraska 0-8 tourney history.

## Split Decisions (2)

1. **Game 4: UConn over UCLA** — Matchup analyst dissented (UCLA 3PT differential, Dent A/TO). Statistical tiebreaker gave UConn.
2. **Game 10: Arkansas over Wisconsin** — Matchup + Recency picked Wisconsin (3PT volume vs poor Arkansas D). Statistical tiebreaker gave Arkansas on KenPom gap.

## Key Learnings

- **Split decisions are rare but real.** 2 of 10 games had data-agent disagreement. Both involved teams with clear schematic exploits going both ways.
- **5-over-4 upsets are analytically common.** Both upsets were 5-seeds rated higher by advanced metrics.
- **Injury context carries forward.** Wilson (UNC), Knox (Arkansas), Foster (Duke), Hodge (Nova) — all factored into picks.
- **Agent search quality is solid.** BPI, Sports Reference, and beat reports provide sufficient data. KenPom/EvanMiya gaps persist.
- **~5% context per game** holds as a good estimate.

## Remaining Matchups (6 games)

### West Region (2 remaining)
- Game 11: **BYU (6) vs Gonzaga (3)** — Dybantsa (25.3 PPG, best player on floor) vs Gonzaga 30-3, 66.0 PPG allowed. 6v3 ~39% upset rate. Both missing key players (Saunders/Traore for BYU, Huff for Gonzaga). High-profile matchup.
- Game 12: **Miami (7) vs Purdue (2)** — Purdue ORtg 124.7 (#2), Big Ten champs. Miami won R64 by stat tiebreaker (57%, split). Miami has injury concerns.

### Midwest Region (4 remaining)
- Game 13: **Michigan (1) vs Saint Louis (9)** — Michigan SRS #1, 31-3, 19-1 Big Ten. SLU 28-5, elite opp eFG% (#2), opp 3PT% (#8). Avila matchup anomaly flagged.
- Game 14: **Akron (12) vs Alabama (4)** — Akron upset TTU (Toppin ACL) in R64, on 10-game streak. Alabama's Holloway suspended, 291st DRtg, 9 scholarship players. Top upset candidate.
- Game 15: **Tennessee (6) vs Virginia (3)** — Virginia 29-5, DRtg #16, BPG #1 nationally. Tennessee OREB #2, Barnes 12-7 in tourney. Defensive battle.
- Game 16: **Kentucky (7) vs Iowa State (2)** — ISU BPI top-10, elite ball security (10.3 TO/game). Kentucky depleted (Quaintance doubtful, Knox/Lowe OUT). Strong ISU favorite.

## How to Resume

Start a new session and say: **"Resume the round-of-32 analysis from the checkpoint."**

Read:
- `output/round-of-32/checkpoint.json` for progress state
- `output/round-of-32/HANDOFF.md` (this file) for context
- `output/round-of-32/picks.json` for completed picks
- Agent prompts from `agents/*.md`

Start with **Game 11: BYU (6) vs Gonzaga (3) — West Region**.
