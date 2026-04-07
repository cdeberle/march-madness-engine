# Championship — Retrospective

**Status**: COMPLETE
**Final Record**: 0-1 (0.0%)
**Last updated**: 2026-04-07

---

## Misses (1)

### MISS: Michigan (1) vs UConn (2) — STRUCTURAL MISS

**Prediction**: Duke at 58% (split)
**Result**: Michigan 69, UConn 63

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Arizona | No |
| Matchup | Duke | No |
| Recency | Arizona | No |
| Historical | Duke | No |

**What happened**: Neither projected finalist made the championship game. Duke was eliminated by UConn in the Elite 8 (73-72 on Mullins' 35-foot three with 0.4 seconds left). Arizona was eliminated by Michigan in the Final Four (91-73 blowout). The actual championship was Michigan vs UConn — two teams the engine had eliminated before the Elite 8.

The game itself: Michigan won its first national title since 1989, beating UConn 69-63 in a defensive grind. Michigan shot just 38.2% from the floor and 2-of-13 from three (13.3%) but won it at the free throw line — 25-of-28 (89.3%). Elliot Cadeau led all scorers with 19 points. Tarris Reed Jr. had a double-double (13 pts, 14 reb). Yaxel Lendeborg gutted through 36 minutes on a sprained MCL and bone bruise suffered in the Arizona game, finishing with 13 points. Alex Karaban led UConn with 17 points and 11 rebounds. UConn's bid for a third title in four years was denied.

**Lesson**: This was a structural miss — the engine had no analysis for this matchup. The root cause traces back to two critical earlier misses: (1) UConn over Duke in the E8, decided by a 0.4-second miracle shot, and (2) Michigan over Arizona in the F4, where the Matchup Analyst was right but overruled. Had the engine's tiebreaker weighted schematic fit over roster availability in the F4, it would have had Michigan in the title game — though still against Duke, not UConn.

---

## Tournament Summary

### Final Record by Round
| Round | Record | Accuracy |
|-------|--------|----------|
| Round of 64 | 24-8 | 75.0% |
| Round of 32 | 11-5 | 68.8% |
| Sweet 16 | 5-3 | 62.5% |
| Elite 8 | 2-2 | 50.0% |
| Final Four | 0-2 | 0.0% |
| Championship | 0-1 | 0.0% |
| **Total** | **42-21** | **66.7%** |

### Confidence Calibration (All Rounds)
| Confidence Bucket | Record | Hit Rate | Expected | Calibrated? |
|-------------------|--------|----------|----------|-------------|
| 50-59% | 12-9 | 57.1% | ~55% | Good |
| 60-69% | 14-7 | 66.7% | ~65% | Good |
| 70-79% | 9-3 | 75.0% | ~75% | Good |
| 80-89% | 5-1 | 83.3% | ~85% | Good |
| 90-100% | 2-1 | 66.7% | ~95% | Under |

### Agent Accuracy (All Rounds)
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 40-23 | 63.5% |
| Matchup | 42-21 | 66.7% |
| Recency | 40-23 | 63.5% |
| Historical | 35-28 | 55.6% |

*Note: Confidence calibration and agent accuracy are approximate aggregates across all 63 games. Per-round exact figures are in each round's retrospective. When a game was a structural miss (projected matchup didn't happen), all agents are marked incorrect.*

### Key Tournament-Wide Patterns

1. **The engine was well-calibrated through the first four rounds.** 42-18 (70.0%) through the Elite 8 with confidence buckets tracking expected rates. The collapse was concentrated in the final three games (0-3), two of which were structural misses from cascading bracket failures.

2. **The South region was catastrophic.** From R32 onward, the engine went 0-for-everything in the South. Iowa over Florida broke the bracket in R32, and every downstream pick was invalidated. This single region accounted for the majority of the engine's structural misses.

3. **The Matchup Analyst was the best agent.** 66.7% accuracy, the highest of any agent, and it was right on the two most consequential late-tournament calls: Michigan over Arizona (F4, overruled by tiebreaker) and Michigan over Iowa State (E8). Its schematic analysis — identifying specific strength-on-weakness collisions rather than aggregate efficiency — proved most predictive in high-stakes games between elite teams.

4. **The Historical Analyst was the worst agent.** 55.6% accuracy — barely better than a coin flip. Its reliance on institutional pedigree and seed history was the least predictive lens. The one area it added value: coaching pedigree (Hurley's UConn, Dusty May's rebuild) — but it consistently underweighted this in its confidence scores.

5. **Tiebreaker protocol needs revision.** Two split-decision games used the situational tiebreaker: F4 Game 2 (Arizona over Michigan, wrong — roster availability) and Championship (Duke over Arizona, structurally moot). The Matchup Analyst's schematic case should carry more weight than roster gaps when it identifies a direct structural counter to the opponent's offensive identity.

6. **Miracle shots are real and unmodelable.** Two of the engine's cleanest misses — Kentucky/Santa Clara (R64) and Duke/UConn (E8) — were decided by buzzer-beating shots from 35+ feet. The Duke miss cascaded into structural misses for the entire East bracket from the Final Four onward. No analytical framework can account for these; the engine's read was correct for 39+ minutes in both games.

7. **Michigan was the tournament's best team and the engine almost saw it.** The engine correctly picked Michigan in every round they appeared (R64 through E8 — 4-0). It only missed Michigan in the Final Four, where the tiebreaker overruled the Matchup Analyst. Michigan finished 37-3, won 6 tournament games by an average of 17.5 points (except the 6-point championship), and Dusty May's transfer portal rebuild earned him National Coach of the Year.

### The Actual Champion: Michigan Wolverines (37-3)

First national title since 1989. First Big Ten champion since Michigan State in 2000. Built almost entirely through the transfer portal by Dusty May in two years. Won the title shooting 13.3% from three — on free throws and defense.
