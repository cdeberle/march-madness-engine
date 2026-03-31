# Sweet 16 — Retrospective

**Status**: COMPLETE
**Final Record**: 5-3 (62.5%)
**Last updated**: 2026-03-31

---

## Hits (5)

### HIT: (1) Duke over (5) St. John's — 72% confidence
Consensus: unanimous | All agents correct: yes
Duke 80-75. Duke rallied from a 10-point second-half deficit. Evans scored 25, Boozer 22/10. Caleb Foster returned from foot surgery and scored 11 in the second half. Engine correctly identified Duke's efficiency gap as insurmountable despite SJU's Ejiofor (17/8/6). Closer than projected but the right call.

### HIT: (2) UConn over (3) Michigan State — 57% confidence
Consensus: protocol_override | All agents correct: no (Statistical picked MSU)
UConn 67-63. UConn built a 19-point lead, survived MSU's comeback. Reed (20) and Karaban (17) sealed it with late FTs. MSU shot 4-of-16 from three — the engine's thesis that UConn's top-10 block rate and 45.2% opp 2PT would suppress MSU's interior offense was validated perfectly. The protocol override that vacated Statistical's low-conviction MSU pick (52%) was the correct call. One of the engine's best process decisions.

### HIT: (1) Arizona over (4) Arkansas — 68% confidence
Consensus: unanimous | All agents correct: yes
Arizona 109-88. Dominant — Arizona shot 64% from the field (37-of-58), highest by any Sweet 16+ team since 2016 Villanova. Six players scored 14+, a first in NCAA tournament history: Burries 21, Peat 21, Kharchenkov 15, Bradley 14, Krivas 14, Awaka 14. Acuff had 28 for Arkansas but it was never close. The engine's "~24-point efficiency gap, largest in any Sweet 16 matchup" thesis was dramatically validated. Confidence was actually too low.

### HIT: (2) Purdue over (11) Texas — 63% confidence
Consensus: split | Matchup agent incorrect (picked Gonzaga — wrong opponent)
Purdue 79-77. Kaufman-Renn's tip-in with 0.7 seconds left won it. 16 lead changes, 10 ties. Texas's Tramon Mark had 29. Engine correctly identified Purdue advancing despite analyzing against Gonzaga (eliminated in R32). Purdue's #1 offense and Kaufman-Renn's interior presence were the right calls regardless of opponent.

### HIT: (1) Michigan over (4) Alabama — 81% confidence
Consensus: unanimous | All agents correct: yes
Michigan 90-77. Lendeborg 23/12. Engine projected Michigan vs Akron but correctly identified Michigan as the advancing team. Alabama's Philon had 35 but the Tide shot 14-of-47 from three (30%) against Michigan's #1 defense. Engine's thesis of Michigan's defensive dominance against any opponent held.

---

## Misses (3)

### MISS: Iowa (9) vs Nebraska (4) — STRUCTURAL MISS

**Prediction**: Florida at 62% (split)
**Result**: Iowa 77, Nebraska 71

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Florida | No |
| Matchup | Vanderbilt | No |
| Recency | Florida | No |
| Historical | Florida | No |

**What happened**: Both projected teams (Florida, Vanderbilt) were eliminated in R32 — Florida by Iowa (73-72) and Vanderbilt by Nebraska (74-72). The engine had zero analysis for this actual matchup. Iowa trailed for 32 minutes but won after Nebraska's infamous 4-players-on-the-court gaffe in crunch time gave Folgueiras a free three-point play that proved decisive.
**Lesson**: This is a cascading bracket failure, not an analytical miss. When R32 upsets invalidate an entire Sweet 16 slot, the engine needs a mechanism to re-analyze from scratch rather than carrying forward dead picks. The South region was the engine's weakest — it missed Iowa over Florida and Vanderbilt over Nebraska, then had no valid pick for the resulting matchup.

---

### MISS: (3) Illinois over (2) Houston — 65% confidence

**Prediction**: Houston at 65% (unanimous)
**Result**: Illinois 65, Houston 55

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Houston | No |
| Matchup | Houston | No |
| Recency | Houston | No |
| Historical | Houston | No |

**What the engine saw**: Houston's #5 DRtg (90.2, 62.9 PPG allowed) purpose-built to suppress Illinois's #1 AdjOE. Near-home-court at Toyota Center. Sampson 31-21 in tourney vs Underwood 8-9. Houston's guard trio targeting Illinois's perimeter weakness.
**What the engine missed**: Illinois went on a 17-0 run spanning nearly 7 minutes to build a 44-26 lead. Mirkovic (14/10) and Wagler (13/12 career high) dominated the glass. Houston shot just 34% from the field (22-64) — their offense, not their defense, was the problem. The engine correctly flagged Illinois's elite offense as the "Kill Shot" lever but still picked Houston. The Toyota Center "home court" factor was real but insufficient when Houston couldn't score.
**Confidence delta**: 65% unanimous was overconfident on a 2-vs-3 matchup where the engine's own analysis identified the opponent's #1 offense as a lethal threat.
**Lesson**: When the engine flags a team as having the highest "Kill Shot" rating in the field, 65% confidence against them is internally inconsistent. The engine identified Illinois's ceiling but bet against it. In 2-vs-3 games, defensive reputation should not override the opponent's offensive ceiling when that ceiling is historically elite.

---

### MISS: (6) Tennessee over (2) Iowa State — 76-62

**Prediction**: Iowa State at 67% (unanimous)
**Result**: Tennessee 76, Iowa State 62

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Iowa State | No |
| Matchup | Iowa State | No |
| Recency | Iowa State | No |
| Historical | Iowa State | No |

**What the engine saw**: ISU NET #6, pressure D forces TOs on 21.9% of possessions. Demolished ASU 91-42. Momcilovic's 49.6% 3PT stretches defense. Virginia (projected opponent) would struggle with ISU's pressure.
**What the engine missed**: Actual opponent was Tennessee (Virginia eliminated in R32). Tennessee dominated the glass 43-22 with 16 offensive rebounds, scoring 42 points in the paint. ISU's perimeter-dependent offense had no answer for Tennessee's interior physicality. This is the same "power conference physicality overwhelms perimeter-dependent teams" pattern from R64 (Saint Mary's/A&M, Akron/TTU). The engine projected Iowa State vs Virginia's Pack Line — Tennessee's rebounding-and-physicality identity is a completely different matchup profile.
**Confidence delta**: 67% was too high given the opponent mismatch — the analysis was built against Virginia, not Tennessee.
**Lesson**: When the actual opponent differs from the projected one, the original analysis is directionally unreliable. Tennessee's rebounding dominance is exactly the kind of matchup-specific factor that changes the outcome. ISU's pressure defense, which the engine weighted heavily, is less effective against teams that win through interior play rather than perimeter shooting. This repeats the R32 Gonzaga/Texas structural miss.

---

## Round Summary: Sweet 16

**Record**: 5-3 (62.5%)
**Upsets correctly called**: 0 of 3 (Iowa over Nebraska, Illinois over Houston, Tennessee over Iowa State)
**Upsets missed**: 3
**False upset calls**: 0
**Structural misses**: 1 (Iowa vs Nebraska — projected matchup never happened)

### Confidence Calibration
| Confidence Bucket | Record | Hit Rate | Expected | Calibrated? |
|-------------------|--------|----------|----------|-------------|
| 50-59% | 1-0 | 100% | ~55% | Over — small sample |
| 60-69% | 2-3 | 40% | ~65% | Under — repeat of R64's soft-lean problem |
| 70-79% | 1-0 | 100% | ~75% | Over — small sample |
| 80-89% | 1-0 | 100% | ~85% | Over — small sample |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 4-4 | 50.0% |
| Matchup | 4-4 | 50.0% |
| Recency | 5-3 | 62.5% |
| Historical | 5-3 | 62.5% |

### Key Patterns

1. **The 60-69% zone remains the engine's weakness.** 2-3 (40%) in this bucket, consistent with R64's 55.6% and R32's 67%. The engine's "soft lean" picks continue to be overconfident.

2. **Opponent mismatch problem compounded.** 2 of 3 misses involved opponents the engine didn't analyze (Iowa/Nebraska structural void, Tennessee replacing Virginia). The R32 retrospective flagged this exact issue — the engine still has no mechanism to re-analyze when upsets change the bracket.

3. **Unanimous consensus on misses — again.** Both non-structural misses (Houston, Iowa State) were unanimous. When all 4 agents agree and the game is decided by double digits the wrong way (Illinois by 10, Tennessee by 14), the consensus was false certainty built on flawed premises.

4. **Protocol override worked when used.** The UConn pick (vacating Statistical's low-conviction MSU pick) was one of the round's best calls. When the override follows its own rules, it adds value.

5. **"Defensive reputation > offensive ceiling" bias.** The Houston miss repeats a pattern: the engine bets on elite defenses over elite offenses. Houston's #5 DRtg was the thesis; Illinois's #1 AdjOE was flagged but overridden. When two historically elite units collide, the engine defaults to defense — but in this tournament, offense has won those collisions.

6. **Power conference physicality pattern continues.** Tennessee's 43-22 rebounding margin over Iowa State echoes Texas A&M's 18 forced turnovers against Saint Mary's and TTU holding Akron 17 below average. Interior physicality remains the engine's blind spot.

### Cumulative Record (R64 + R32 + Sweet 16)
- **R64**: 24-8 (75.0%)
- **R32**: 11-5 (68.8%)
- **Sweet 16**: 5-3 (62.5%)
- **Combined**: 40-16 (71.4%)
