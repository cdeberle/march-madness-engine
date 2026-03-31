# Elite 8 — Retrospective

**Status**: COMPLETE
**Final Record**: 2-2 (50.0%)
**Last updated**: 2026-03-31

---

## Hits (2)

### HIT: (1) Arizona over (2) Purdue — 66% confidence
Consensus: unanimous | All agents correct: yes
Arizona 79-64. Arizona trailed 38-31 at halftime — the largest halftime deficit they faced all season — then erupted with a 16-3 run to start the second half. Freshmen Peat (20), Kharchenkov (18), and Burries (14) combined for 52 points. Arizona held Purdue's Smith/Kaufman-Renn/Loyer to 12-of-38 shooting. The engine's thesis — Arizona's DRtg +11.0 gap and paint dominance against Purdue's 342nd rim defense — played out exactly. Arizona's first Final Four since 2001.

### HIT: (1) Michigan over (6) Tennessee — 62% confidence
Consensus: majority (Historical dissented with Iowa State) | 3 of 4 agents correct
Michigan 95-62. Blowout — Michigan went on a 21-0 run in 4:42 in the second half. Lendeborg 27 points on 10-of-19 shooting, Cadeau 8/10 ast. Engine correctly identified Michigan advancing despite analyzing against Iowa State (eliminated by Tennessee in S16). Michigan's #1 defense and interior size dominated regardless of opponent — the thesis was opponent-agnostic. Michigan's first Final Four since 2018.

---

## Misses (2)

### MISS: (2) UConn over (1) Duke — 73-72

**Prediction**: Duke at 64% (unanimous)
**Result**: UConn 73, Duke 72

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Duke | No |
| Matchup | Duke | No |
| Recency | Duke | No |
| Historical | Duke | No |

**What the engine saw**: Duke's ~10.7 AdjEM and 6.2 BPI efficiency margins crossed the high-confidence threshold. Boozer's matchup-proof scoring. Ngongba uncertain but Duke's depth sufficient.
**What the engine missed**: UConn mounted one of the most historic comebacks in tournament history — rallying from a **19-point deficit** (44-25 late in the first half). Duke became the first #1 seed in tournament history to lose after leading by 15+ at halftime (that scenario was previously 134-0). The winning play: Braylon Mullins — a freshman who had been recruited by Duke and rejected them — hit a 35-foot three-pointer with **0.4 seconds left** to give UConn their first lead since the opening minute. Tarris Reed Jr. led UConn with 26 points (10-of-16, 4 blocks). Boozer had 27/8/4/2 for Duke. The engine's analysis was validated for 39 minutes — Duke dominated and the efficiency gap played out. Then one shot erased everything.
**Confidence delta**: 64% on a game that Duke led by 19 and lost by 1. The engine's read was directionally correct — Duke was the better team for 39.6 of 40 minutes. This is the Kentucky/Santa Clara pattern from R64: analytically sound pick undone by a once-in-a-decade shot.
**Lesson**: As with Kentucky's half-court buzzer-beater in R64, no analytical framework can account for a 35-foot three with 0.4 seconds left. The engine identified the right favorite. Hurley's tournament pedigree (back-to-back titles, now third Final Four in four years) was underweighted — Historical had Duke at just 57%, the lowest of any agent. Tournament coaching experience matters more in close games where late-game execution decides outcomes.

---

### MISS: Illinois (3) vs Iowa (9) — STRUCTURAL MISS

**Prediction**: Houston at 57% (split)
**Result**: Illinois 71, Iowa 59

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Houston | No |
| Matchup | Florida | No |
| Recency | Houston | No |
| Historical | Florida | No |

**What happened**: Both projected teams (Florida, Houston) were eliminated before the Elite 8. Florida lost to Iowa in R32; Houston lost to Illinois in the Sweet 16. The engine had zero analysis for this matchup. Illinois was tied 51-51 with 7:14 remaining, then went on a 20-8 run to close. Wagler led with 25 (14 in second half), Stojakovic 17, Ivisic 13. Illinois dominated the glass +17 (38-21) and outscored Iowa 40-12 in the paint. Iowa's Stirtz had 24 but couldn't overcome Illinois's interior dominance.
**Lesson**: This is the second consecutive structural miss in the South region. The cascading bracket failure from R32 (Iowa over Florida, Nebraska over Vanderbilt) and Sweet 16 (Illinois over Houston) meant the engine had no valid analysis for either South region game from the Sweet 16 onward. The South was the engine's catastrophic region — every pick from R32 onward was invalidated.

---

## Round Summary: Elite 8

**Record**: 2-2 (50.0%)
**Upsets correctly called**: 0 of 1 (UConn over Duke)
**Upsets missed**: 1 (UConn over Duke)
**False upset calls**: 0
**Structural misses**: 1 (Illinois vs Iowa — projected matchup never happened)

### Confidence Calibration
| Confidence Bucket | Record | Hit Rate | Expected | Calibrated? |
|-------------------|--------|----------|----------|-------------|
| 50-59% | 0-1 | 0% | ~55% | Under — structural miss |
| 60-69% | 2-1 | 67% | ~65% | Good |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 2-2 | 50.0% |
| Matchup | 2-2 | 50.0% |
| Recency | 2-2 | 50.0% |
| Historical | 1-3 | 25.0% |

### Key Patterns

1. **The South region was a total loss.** From R32 onward, every South region pick was wrong or structurally invalidated. The cascade: Iowa upset Florida (R32) → Illinois upset Houston (S16) → Illinois beat Iowa (E8). The engine predicted Florida → Houston → Houston for this path. Zero correct picks in the South from R32 through E8.

2. **Miracle shots are unmodelable — and that's OK.** The Duke/UConn miss mirrors the Kentucky/Santa Clara R64 miss. Both games featured the engine's pick leading in the final seconds, then losing to a once-in-a-decade shot (half-court buzzer-beater, 35-foot three with 0.4 seconds). The engine was analytically correct in both cases. Two of the engine's four total "clean" misses across S16+E8 were decided by final-seconds miracles.

3. **When the engine is right, it's dominant.** Arizona 79-64 and Michigan 95-62 — the two hits were emphatic blowouts. The engine's high-confidence picks on 1-seeds with elite defenses continued to be money.

4. **Historical agent collapsed.** 1-3 (25.0%) — worst performance of any agent in any round. Its dissent on Michigan (picking Iowa State) was wrong. Its failure to weight UConn's coaching pedigree cost it on the Duke game.

### Cumulative Record (R64 through Elite 8)
- **R64**: 24-8 (75.0%)
- **R32**: 11-5 (68.8%)
- **Sweet 16**: 5-3 (62.5%)
- **Elite 8**: 2-2 (50.0%)
- **Combined**: 42-18 (70.0%)

### Final Four Implications
The actual Final Four is:
- **(2) UConn vs (3) Illinois** (East vs South)
- **(1) Arizona vs (1) Michigan** (West vs Midwest)

The engine's projected Final Four was Duke vs Houston and Arizona vs Michigan. Only the West vs Midwest semifinal (Arizona vs Michigan) materialized as predicted. Duke and Houston were both eliminated — Duke by a 0.4-second three, Houston by Illinois's elite offense. The engine's championship pick (Duke over Arizona) is no longer possible.
