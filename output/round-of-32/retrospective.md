# Round of 32 Retrospective

Generated: 2026-03-23

---

## Context

8 of 16 R32 matchups differed from projections due to R64 upsets (TCU replaced Ohio State, Louisville replaced South Florida, Texas A&M replaced Saint Mary's, High Point replaced Wisconsin, Texas replaced BYU, Miami replaced Missouri, Texas Tech replaced Akron, Kentucky replaced Santa Clara). Picks are evaluated on whether the engine correctly identified the team that advanced to the Sweet 16.

---

### MISS: (1) Florida vs (9) Iowa

**Prediction**: Florida at 83% (unanimous)
**Result**: Iowa won 73-72

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Florida | No |
| Matchup | Florida | No |
| Recency | Florida | No |
| Historical | Florida | No |

**What the engine saw**: Florida #1 rebounding nationally (+15.3 margin), NET #4 vs #27, SEC DPOY Chinyelu dominating interior, defending champs in home-state Tampa, Q1 record 12-6 vs Iowa 5-9.
**What the engine missed**: Iowa's Stirtz (20.2 PPG) was flagged as the upset lever but underweighted. The engine treated the rebounding mismatch as "insurmountable" when a single late 3-pointer (Folgueiras) can render a 40-minute rebounding advantage irrelevant. One-possession games are structurally unpredictable — 83% confidence on any 1v9 with a legitimate All-American guard on the other side was too high.
**Confidence delta**: 83% confidence was far too high for a game decided by 1 point. This was the round's worst calibration miss.
**Lesson**: Interior dominance metrics (rebounding, paint scoring) don't protect against perimeter-shooting variance in single-elimination. Discount rebounding advantages when the underdog has elite guard play capable of bypassing the paint entirely.

---

### MISS: (5) Vanderbilt vs (4) Nebraska

**Prediction**: Vanderbilt at 59% (unanimous) — UPSET PICK
**Result**: Nebraska won 74-72

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Vanderbilt | No |
| Matchup | Vanderbilt | No |
| Recency | Vanderbilt | No |
| Historical | Vanderbilt | No |

**What the engine saw**: Vandy BPI #14 vs Nebraska #18, ORtg 121.1 vs 114.0, beat #1 Florida by 17 in SEC Tourney, #1 block rate nationally. Nebraska 0-8 all-time in tourney.
**What the engine missed**: Nebraska's elite defense (DRtg 97.7, 29% opp 3PT) was flagged as the key counter but overridden. The 2-point margin confirms this was a genuine coin-flip — the engine's analysis even called Nebraska's defensive ceiling the win condition. Nebraska's first-ever tourney win proves the 0-8 historical record was noise, not signal.
**Confidence delta**: 59% was appropriately uncertain — this was a true coin-flip and the narrowest miss of the round.
**Lesson**: When the engine flags a specific counter-thesis (Nebraska's defense holding Vandy below 100 ORtg) and the game is a coin-flip by confidence, treat the counter-thesis as equally valid. 4v5 games should rarely exceed 58% confidence either direction.

---

### MISS: (11) Texas vs (3) Gonzaga

**Prediction**: Gonzaga at 66% (unanimous)
**Result**: Texas won 74-68

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Gonzaga | No |
| Matchup | Gonzaga | No |
| Recency | Gonzaga | No |
| Historical | Gonzaga | No |

**What the engine saw**: Gonzaga 30-3, #1 paint dominance (44.7 scored, 25.1 allowed), Ike 19.7/8.2 on 57.3% FG, Q1 6-1. BYU missing Saunders + Traore.
**What the engine missed**: The analysis was built against BYU (the projected opponent), not Texas. Texas upset BYU in R64 (79-71) and brought a completely different matchup profile. The engine noted Dybantsa as a ~35% upset lever but analyzed BYU's depleted roster, not Texas's full-strength squad. This is a structural failure — analyzing the wrong opponent means the matchup-specific factors were irrelevant.
**Confidence delta**: 66% against the wrong opponent is unratable. Against Texas specifically, the engine had no analysis.
**Lesson**: When R64 upsets produce a different R32 opponent than projected, the original analysis is invalidated. The engine re-analyzed some games (VCU replacing UNC, Missouri replacing Miami) but not all. All R32 analyses with wrong opponents needed re-evaluation.

---

### MISS: (12) Akron vs (4) Alabama

**Prediction**: Akron at 56% (recency_override) — UPSET PICK
**Result**: Alabama won 90-65 (actual opponent: Texas Tech)

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Akron | No |
| Matchup | Alabama | Yes |
| Recency | Akron | No |
| Historical | Alabama | Yes |

**What the engine saw**: Holloway suspended (felony, 16.8 PPG), Alabama down to 9 scholarship players, DRtg 291st. Akron top-10 offense, three 40%+ 3PT shooters, 10-game win streak.
**What the engine missed**: Akron lost to Texas Tech 91-71 in R64 — this pick was dead before R32 started. The Holloway suspension thesis was valid (Alabama's defense is genuinely terrible) but the recency override picked the wrong upset beneficiary. Alabama then demolished Texas Tech 90-65, suggesting the engine dramatically overweighted the Holloway impact on a team that still has Philon (21.5 PPG) and enough talent to beat mid-majors and Big 12 middle-tier opponents comfortably.
**Confidence delta**: 56% on a team that didn't make R32 is a structural error, not a calibration error.
**Lesson**: Recency overrides based on roster changes (suspensions, injuries) should only adjust confidence, not flip picks — especially when 2 of 4 agents still favored the other side. The Holloway suspension was real but didn't make Alabama worse than Texas Tech or Akron.

---

### MISS: (6) Tennessee vs (3) Virginia

**Prediction**: Virginia at 61% (unanimous)
**Result**: Tennessee won 79-72

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Virginia | No |
| Matchup | Virginia | No |
| Recency | Virginia | No |
| Historical | Virginia | No |

**What the engine saw**: Virginia 29-5, NET #13, BPG #1 nationally (Onyenso 3.0 BPG), shot-blocking counters Tennessee's #2 OREB. Q1 8-4, played Duke within 4 in ACC final. Tennessee on late-season slide (4 of last 6 losses).
**What the engine missed**: Tennessee's 79 points blew through Virginia's shot-blocking wall. The engine treated shot-blocking as a direct counter to offensive rebounding, but Tennessee scored at will despite it. Tennessee's late-season slide was noise — they beat Miami (OH) 78-56 in R64 showing the talent was still there. The 6v3 upset rate (~39% historically per our own analysis) should have kept this closer to a coin-flip.
**Confidence delta**: 61% was not wildly overconfident but the unanimous consensus masked legitimate uncertainty. When the historical agent's own data says 6-seeds win ~39% of the time, unanimous agreement at 61% is internally inconsistent.
**Lesson**: When the historical upset rate for a seed matchup is 35-40%, the pick confidence should rarely exceed 62-63% regardless of team-level analytics. The base rate is screaming "close game" and the engine ignored it.

---

### HIT: (1) Duke over (9) TCU — 84% confidence
Consensus: unanimous | All agents correct: yes
Note: Actual opponent was TCU (projected Ohio State). Duke won 81-58 — dominant regardless of opponent.

### HIT: (5) St. John's over (4) Kansas — 60% confidence | UPSET CORRECTLY CALLED
Consensus: unanimous | All agents correct: yes
SJU's defensive pressure thesis validated perfectly. Darling buzzer-beater (67-65) confirms this was the coin-flip the engine said it was. Correctly identified SJU as the better analytics team despite lower seed.

### HIT: (3) Michigan State over (6) Louisville — 71% confidence
Consensus: unanimous | All agents correct: yes
Note: Actual opponent was Louisville (projected South Florida). MSU won 77-69.

### HIT: (2) UConn over (7) UCLA — 68% confidence
Consensus: split | 3 of 4 agents correct (Matchup picked UCLA)
UConn's defensive edge (DRtg 97.9) held UCLA to 57 points. Karaban's huge game validated the talent thesis. Matchup analyst's UCLA dissent (3PT differential, Dent's A/TO) didn't materialize — UCLA shot poorly.

### HIT: (3) Illinois over (11) VCU — 64% confidence
Consensus: unanimous | All agents correct: yes
Illinois's #1 AdjOE overwhelmed Havoc. 76-55 was more dominant than the 64% confidence suggested. VCU never got clean transition looks.

### HIT: (2) Houston over (10) Texas A&M — 71% confidence
Consensus: unanimous | All agents correct: yes
Note: Actual opponent was Texas A&M (projected Saint Mary's). Houston's defense suffocated another opponent — 88-57 blowout.

### HIT: (1) Arizona over (9) Utah State — 79% confidence
Consensus: unanimous | All agents correct: yes
Rebounding mismatch played out exactly as predicted. Arizona 78-66.

### HIT: (4) Arkansas over (12) High Point — 57% confidence
Consensus: split | 2 of 4 agents correct (Matchup/Recency picked Wisconsin)
Note: Actual opponent was High Point (projected Wisconsin). Arkansas won 94-88 in a high-scoring affair. Acuff's offensive ceiling thesis validated. The split consensus and 57% confidence were appropriate for this volatile matchup.

### HIT: (2) Purdue over (7) Miami — 69% confidence
Consensus: unanimous | All agents correct: yes
Note: Actual opponent was Miami (projected Missouri). Purdue's #1 offense powered through, 79-69.

### HIT: (1) Michigan over (9) Saint Louis — 81% confidence
Consensus: unanimous | All agents correct: yes
Michigan's #1 defense and interior length dominated. 95-72 blowout validated the high confidence.

### HIT: (2) Iowa State over (7) Kentucky — 79% confidence
Consensus: unanimous | All agents correct: yes
Note: Actual opponent was Kentucky (projected Santa Clara). ISU's turnover-forcing identity crushed Kentucky's chronic TO weakness. 82-63.

---

## Round Summary: Round of 32

**Record**: 11-5 (68.8%)
**Upsets correctly called**: 1 of 4 (St. John's over Kansas)
**Upsets missed**: 3 (Iowa over Florida, Texas over Gonzaga, Tennessee over Virginia)
**False upset calls**: 2 (Vanderbilt over Nebraska, Akron over Alabama)

### Confidence Calibration
| Confidence Bucket | Record | Expected | Calibrated? |
|-------------------|--------|----------|-------------|
| 50-59% | 1-2 (33%) | ~55% | Over — low-confidence picks underperformed |
| 60-69% | 4-2 (67%) | ~65% | Good |
| 70-79% | 4-0 (100%) | ~75% | Over — small sample but outperformed |
| 80-89% | 2-1 (67%) | ~83% | Under — Florida miss at 83% dragged this down |
| 90-100% | N/A | N/A | No picks in this bucket |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 11-5 | 68.8% |
| Matchup | 10-6 | 62.5% |
| Recency | 10-6 | 62.5% |
| Historical | 12-4 | 75.0% |

### Key Patterns
- **Historical analyst was most accurate (75%)** — its base-rate awareness (seed matchup win rates, coaching records, program pedigree) outperformed the data-heavy agents this round. This is a reversal from R64 expectations.
- **Opponent mismatch problem**: 8 of 16 games had different opponents than projected. The engine re-analyzed only 2 (VCU replacing UNC, Missouri replacing Miami). Of the 6 unremediated mismatches, 2 were misses (Texas over Gonzaga, Akron not in game). The Gonzaga miss was directly caused by analyzing against BYU's depleted roster instead of Texas's full-strength squad.
- **Upset detection regressed**: R64 went 3-for-5 on upsets called; R32 went 1-for-4. The 3 missed upsets were all lower seeds beating 1-3 seeds — the engine's confidence in top seeds was systematically too high.
- **Low-confidence picks underperformed**: The 50-59% bucket went 1-2. The engine is slightly overconfident on its upset calls — when it says "barely favor the underdog," the favorite still wins more often than not.
- **Unanimous consensus masked uncertainty**: All 5 misses were unanimous or near-unanimous. When every agent agrees and the game is decided by 1-2 points (Iowa 73-72, Nebraska 74-72), the consensus was false certainty.
- **Florida miss was the costliest**: 83% confidence on a 1-point loss. The engine correctly identified the rebounding mismatch but treated it as deterministic. Single-elimination variance at the margins was underweighted.

### Cumulative Record (R64 + R32)
- **R64**: 24-8 (75.0%)
- **R32**: 11-5 (68.8%)
- **Combined**: 35-13 (72.9%)
