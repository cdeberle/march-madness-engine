# Final Four — Retrospective

**Status**: COMPLETE
**Final Record**: 0-2 (0.0%)
**Last updated**: 2026-04-06

---

## Misses (2)

### MISS: UConn (2) vs Illinois (3) — STRUCTURAL MISS

**Prediction**: Duke at 61% (majority)
**Result**: UConn 71, Illinois 62

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Duke | No |
| Matchup | Duke | No |
| Recency | Duke | No |
| Historical | Houston | No |

**What happened**: Neither projected team made it here. Duke was eliminated by UConn in the Elite 8 (73-72 on a 35-foot three with 0.4 seconds left). Houston was eliminated by Illinois in the Sweet 16. The actual game: UConn led most of the way, hitting 12 three-pointers (a program record for a single game). Illinois cut it to 4 late, but Braylon Mullins — the same freshman whose 35-footer eliminated Duke — hit a dagger three with 52 seconds left to seal it. Tarris Reed Jr. led UConn with 17 points and 11 rebounds. Wagler led Illinois with 20 points but Illinois shot 6-of-26 from three (23.1%). UConn advances to its third title game in four years.
**Lesson**: This is the third consecutive structural miss rooted in the South region collapse. The cascade: Iowa over Florida (R32) → Illinois over Houston (S16) → Illinois over Iowa (E8) → UConn over Illinois (F4). The engine's entire East/South Final Four bracket was invalidated by two early upsets. Once a bracket path breaks, every downstream pick is dead weight. Future consideration: the engine could flag "fragile paths" where a single upset cascades into multiple invalidated picks.

---

### MISS: (1) Michigan over (1) Arizona — 91-73

**Prediction**: Arizona at 57% (split — situational tiebreaker)
**Result**: Michigan 91, Arizona 73

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Arizona | No |
| Matchup | Michigan | **Yes** |
| Recency | Arizona | No |
| Historical | Michigan | **Yes** |

**What the engine saw**: AdjEM essentially tied (<0.1 gap). Agents split 2-2. Tiebreaker went to Arizona on roster availability — Michigan missing Grady (OUT, season) and Cason (OUT, season) vs Arizona at full strength. Engine judged that Michigan's depth was too compromised to absorb adversity.
**What the engine missed**: The Matchup Analyst had it right at 57%. Its thesis: Michigan's elite interior defense (Mara 7'3", 80 blocks) directly counters Arizona's paint-dependent offense, and Arizona's low 3PT attempt rate removes the pressure release valve. That's exactly what happened. Mara went for a career-high 26 points on 11-of-16 shooting with 9 rebounds and 2 blocks. Michigan led 26-10 early — Arizona's largest deficit all season — and the lead ballooned to 30. Arizona never got closer than 17 after halftime. Michigan shot 12-of-27 from three while Arizona's interior game was completely neutralized. The depth concern was real but irrelevant — Michigan was so dominant that the thin rotation never mattered.
**Confidence delta**: 57% Arizona on a game Michigan won by 18. The engine's confidence was appropriately uncertain (near coin-flip), but the tiebreaker logic was wrong. Roster availability broke the tie toward Arizona, but Michigan's schematic advantage was the load-bearing factor, not depth.
**Lesson**: When the Matchup Analyst identifies a direct structural counter (elite rim protector vs paint-dependent offense with no perimeter release valve), that schematic argument should carry more weight in tiebreakers than roster availability. A team can overcome missing rotation players; it can't overcome having its entire offensive identity neutralized. The Matchup Analyst was also right in the E8 (Arizona over Purdue, Michigan over Tennessee) — it had the best read on both teams entering this game.

---

## Round Summary: Final Four

**Record**: 0-2 (0.0%)
**Upsets correctly called**: N/A (no upsets occurred)
**Upsets missed**: 0
**False upset calls**: 0
**Structural misses**: 1 (UConn vs Illinois — projected matchup never happened)

### Confidence Calibration
| Confidence Bucket | Record | Hit Rate | Expected | Calibrated? |
|-------------------|--------|----------|----------|-------------|
| 50-59% | 0-1 | 0% | ~55% | Under |
| 60-69% | 0-1 | 0% | ~65% | Under — structural miss |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 0-2 | 0.0% |
| Matchup | 1-1 | 50.0% |
| Recency | 0-2 | 0.0% |
| Historical | 1-1 | 50.0% |

### Key Patterns

1. **The Matchup Analyst was the smartest agent in the room.** It correctly picked Michigan at 57% in Game 2, identifying the exact schematic dynamic (Mara's rim protection vs Arizona's paint-dependent offense) that decided the game. It was also overruled by the tiebreaker protocol. Across E8 + F4, the Matchup Analyst had the most accurate reads on Michigan and Arizona — the two teams that actually made it this far from the West/Midwest path.

2. **Roster availability is a weaker tiebreaker than schematic fit.** The engine broke the Arizona/Michigan tie on "Michigan is missing two rotation players." Michigan won by 18. The lesson: missing depth matters in close games. When one team has a structural schematic counter to the other's entire offensive identity, depth is secondary. The tiebreaker hierarchy should weight schematic mismatches above roster gaps.

3. **South region cascade is now a five-round failure.** R32 through F4, the South region produced zero correct picks. Iowa over Florida (R32) broke the bracket, and every downstream pick was structurally invalidated. The engine's "full context reset between rounds" rule meant it couldn't adapt — each round re-analyzed projected matchups rather than actual bracket state.

4. **UConn's coaching pedigree was systematically underweighted.** The Historical Analyst flagged Hurley's tournament record in the E8 analysis (15-5, 2 national titles) but only at 57% confidence. UConn is now in its third title game in four years. The engine treated coaching pedigree as a soft factor; in tournament basketball, it may be harder-edged than the data suggests.

### Cumulative Record (R64 through Final Four)
- **R64**: 24-8 (75.0%)
- **R32**: 11-5 (68.8%)
- **Sweet 16**: 5-3 (62.5%)
- **Elite 8**: 2-2 (50.0%)
- **Final Four**: 0-2 (0.0%)
- **Combined**: 42-20 (67.7%)

### Championship Implications
The actual championship game (Monday, April 7):
- **(2) UConn vs (1) Michigan**

The engine's projected championship was Duke vs Arizona — neither team is playing. Key storyline: Michigan's Yaxel Lendeborg appeared to injure his ankle/knee during the Arizona game. He returned with a sleeve and scored 11 but his availability/effectiveness Monday is the biggest X-factor.
