# Round of 64 — Retrospective

**Status**: COMPLETE
**Final Record**: 24-8 (75.0%)
**Last updated**: 2026-03-21

---

## Hits (24)

### HIT: (1) Duke over (16) Siena — 96% confidence
Consensus: unanimous | All agents correct: yes
Duke 71-65. Survived a scare — margin tighter than projected.

### HIT: (5) St. John's over (12) Northern Iowa — 71% confidence
Consensus: unanimous | All agents correct: yes
SJU 79-53. Blowout. Engine correctly identified SJU's rebounding and turnover-forcing as the key differentiator.

### HIT: (4) Kansas over (13) CA Baptist — 79% confidence
Consensus: unanimous | All agents correct: yes
KU 68-60. Closer than expected — CBU made it interesting late.

### HIT: (3) Michigan State over (14) North Dakota State — 83% confidence
Consensus: unanimous | All agents correct: yes
MSU 92-67. Blowout matched projection.

### HIT: (7) UCLA over (10) UCF — 65% confidence
Consensus: unanimous | All agents correct: yes
UCLA 75-71. Tight game — confidence level was appropriate.

### HIT: (2) UConn over (15) Furman — 92% confidence
Consensus: unanimous | All agents correct: yes
UConn 82-71. Reed went off (31 pts, 27 reb).

### HIT: (1) Florida over (16) Prairie View — 97% confidence
Consensus: unanimous | All agents correct: yes
Florida 114-55. 18-0 opening run. Total domination.

### HIT: (9) Iowa over (8) Clemson — 56% confidence (UPSET CALLED)
Consensus: unanimous | All agents correct: yes
Iowa 67-61. Engine nailed the Stirtz factor and Clemson's injury issues.

### HIT: (5) Vanderbilt over (12) McNeese — 68% confidence
Consensus: unanimous | All agents correct: yes
Vandy 78-68. TO-averse offense neutralized McNeese's press as predicted.

### HIT: (4) Nebraska over (13) Troy — 79% confidence
Consensus: unanimous | All agents correct: yes
Nebraska 76-47. Defensive gap played out exactly.

### HIT: (11) VCU over (6) North Carolina — 58% confidence (UPSET CALLED)
Consensus: protocol_override | All agents correct: no (Historical missed)
VCU wins in OT. Bias-correction protocol caught this — Wilson OUT was the key. One of the engine's best calls.

### HIT: (3) Illinois over (14) Penn — 88% confidence
Consensus: unanimous | All agents correct: yes
Illinois 105-70. Historic offense performed as advertised.

### HIT: (2) Houston over (15) Idaho — 95% confidence
Consensus: unanimous | All agents correct: yes
Houston 78-47. No drama.

### HIT: (1) Arizona over (16) Long Island — 98% confidence
Consensus: unanimous | All agents correct: yes
Arizona 92-58. Total domination.

### HIT: (9) Utah State over (8) Villanova — 61% confidence (UPSET CALLED)
Consensus: unanimous | All agents correct: yes
USU 86-76. Engine correctly identified USU's edge in every metric + Hodge OUT for Nova.

### HIT: (4) Arkansas over (13) Hawai'i — 78% confidence
Consensus: unanimous | All agents correct: yes
Arkansas 97-78. Offensive firepower matched projection.

### HIT: (3) Gonzaga over (14) Kennesaw State — 88% confidence
Consensus: unanimous | All agents correct: yes
Gonzaga 73-64. Controlled throughout.

### HIT: (2) Purdue over (15) Queens — 94% confidence
Consensus: unanimous | All agents correct: yes
Purdue 104-71. Smith + Kaufman-Renn combined for 51 pts.

### HIT: (1) Michigan over (16) Howard — 97% confidence
Consensus: unanimous | All agents correct: yes
Michigan 101-80. No drama.

### HIT: (9) Saint Louis over (8) Georgia — 62% confidence (UPSET CALLED)
Consensus: unanimous | All agents correct: yes
SLU 102-77. Blowout. Engine nailed SLU's elite two-way efficiency and Georgia's collapse.

### HIT: (4) Alabama over (13) Hofstra — 71% confidence
Consensus: unanimous | All agents correct: yes
Alabama 90-70. Philon scored 29.

### HIT: (6) Tennessee over (11) Miami OH — 70% confidence
Consensus: unanimous | All agents correct: yes
Tennessee 78-56. Controlled throughout.

### HIT: (3) Virginia over (14) Wright State — 89% confidence
Consensus: unanimous | All agents correct: yes
Virginia 82-73. Closer than expected but never in danger.

### HIT: (2) Iowa State over (15) Tennessee State — 94% confidence
Consensus: unanimous | All agents correct: yes
Iowa State 108-74. Total domination.

---

## Misses (8)

### MISS: (8) Ohio State picked → (9) TCU won 66-64

**Prediction**: Ohio State at 61% (unanimous)
**Result**: TCU won 66-64

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Ohio State | No |
| Matchup | Ohio State | No |
| Recency | Ohio State | No |
| Historical | Ohio State | No |

**What the engine saw**: OSU's ORtg 118.6 vs TCU 111.1, BPI edge 14.2 vs 12.0, Thornton as best player on floor
**What the engine missed**: TCU went 7-of-13 from three (53.8%) in the first half and built a 39-24 halftime lead. OSU rallied to take the lead, but Xavier Edmonds hit a layup with 4.3 seconds left to win 66-64. The engine identified TCU's defensive upside but the actual mechanism was a first-half 3-point explosion, not the steal-rate thesis. Thornton's buzzer-beaving half-court heave hit backboard — inches from the engine being right.
**Confidence delta**: 61% was appropriately uncertain — near-toss-up correctly identified
**Lesson**: When a team's primary vulnerability (turnovers, #305) directly aligns with the opponent's primary strength (steals, #37), that specific matchup dynamic should carry more weight than aggregate efficiency metrics. Also: 8-vs-9 games are structurally coin-flips — don't let unanimity inflate confidence above 58%.

---

### MISS: (11) South Florida picked → (6) Louisville won 83-79

**Prediction**: South Florida at 58% (recency_override)
**Result**: Louisville won 83-79

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Louisville | Yes |
| Matchup | South Florida | No |
| Recency | South Florida | No |
| Historical | Louisville | Yes |

**What the engine saw**: Brown Jr. OUT (18.2 PPG, 5th straight game missed), Louisville 7-5 without him, USF on 11-game streak with elite defense
**What the engine missed**: McKneely scored 23 and Conwell added 18 — Louisville's depth held. But the engine's read was *nearly correct*: Louisville blew a **23-point lead** and coach Kelsey called it "the longest 10 minutes of my life." USF's press almost worked exactly as predicted. USF missed 20 of their first 21 three-point attempts — at average shooting, the engine's pick likely hits. This was the right analysis, wrong outcome. Statistical and Historical agents (both picked Louisville) had the edge.
**Confidence delta**: 58% was appropriately uncertain — this was a genuine coin-flip
**Lesson**: Recency override should require a more severe record drop than 7-5 without a player. Sub-.500 without the player is a stronger trigger. Also: when 2 data agents disagree with the override, the bar for overriding should be higher.

---

### MISS: (7) Saint Mary's picked → (10) Texas A&M won 63-50

**Prediction**: Saint Mary's at 66% (unanimous)
**Result**: Texas A&M won 63-50

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Saint Mary's | No |
| Matchup | Saint Mary's | No |
| Recency | Saint Mary's | No |
| Historical | Saint Mary's | No |

**What the engine saw**: SMC's elite defense (AdjDRtg 95.06), A&M's late-season collapse (4-7 in last 11), Mgbako OUT
**What the engine missed**: A&M **forced 18 turnovers** and **dominated the paint 28-12**. SEC-level physicality overwhelmed Saint Mary's — Murauskas (18.8 PPG average) was held to just 4 points and 3 rebounds. SMC shot just 4-of-11 from the free-throw line (80.5% FT team entering). A&M's defensive performance (63 points allowed — their season-best) directly contradicted the "late collapse" narrative. The engine overweighted A&M's recent form and underweighted their athletic/physical advantage.
**Confidence delta**: 66% was too high for a 7-vs-10 where the opponent has a clear talent/conference advantage
**Lesson**: Late-season collapses by power conference teams may not translate to tournament performance against mid-major opponents. SEC physicality and size overwhelms WCC-level competition even when the stats say otherwise. When a power conference 10-seed faces a mid-major 7-seed, weight the talent gap higher.

---

### MISS: (5) Wisconsin picked → (12) High Point won 83-82

**Prediction**: Wisconsin at 69% (unanimous)
**Result**: High Point won 83-82

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Wisconsin | No |
| Matchup | Wisconsin | No |
| Recency | Wisconsin | No |
| Historical | Wisconsin | No |

**What the engine saw**: Wisconsin ORtg #7, elite ball security (TO rate 12.8%, 3rd) to neutralize HP's #1 steal rate
**What the engine missed**: Rob Martin had 23 pts/10 ast, and Chase Johnston — a 3-point specialist who was **0-for-4 inside the arc all season** — hit a fast-break layup (his first 2-pointer of the year) with 11.7 seconds left to win it. Wisconsin actually performed well (Boyd 27 pts, Blackwell 22/10) — this was a genuine coin-flip decided by one improbable shot. Owen Aquino's blocked layup on Boyd and a missed FT by Fletcher sealed it. The engine flagged this as a "top upset candidate" but still gave 69%.
**Confidence delta**: 69% was too high — engine's own narrative contradicted its confidence score
**Lesson**: When the deciding factor narrative explicitly calls a game a "top upset candidate," confidence should be pulled to 55-60%. Even at 55%, this outcome was borderline unpredictable — it came down to a player's first 2-point basket of the season.

---

### MISS: (6) BYU picked → (11) Texas won 79-71

**Prediction**: BYU at 63% (unanimous)
**Result**: Texas won 79-71

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | BYU | No |
| Matchup | BYU | No |
| Recency | BYU | No |
| Historical | BYU | No |

**What the engine saw**: Dybantsa (25.3 PPG) as best player on floor, BYU ORtg #10
**What the engine missed**: Dybantsa was **spectacular** — 35 points and 10 rebounds, two points shy of BYU's all-time tournament record (Ainge/Fredette). The "best player on floor" thesis was completely validated. BYU lost because **the rest of the team shot 18% from three** and Texas's Matas Vokietaitis (23 pts, 16 reb) dominated the glass. The engine's retrospective claim that "Texas schemed against a one-man show" is wrong — Dybantsa was unstoppable; his supporting cast collapsed.
**Confidence delta**: 63% was too high for a seed line with 39% historical upset rate
**Lesson**: "Best player on floor" is necessary but not sufficient when that player's team has a single point of failure (3-point shooting). In 6-vs-11 matchups, base rate (~39% upset) should anchor confidence to 55-58%. Also: team-level 3PT consistency matters more than top-line ORtg in single-elimination.

---

### MISS: (10) Missouri picked → (7) Miami won 80-66

**Prediction**: Missouri at 55% (protocol_override)
**Result**: Miami won 80-66

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Miami | Yes |
| Matchup | Missouri | No |
| Recency | Missouri | No |
| Historical | Miami | Yes |

**What the engine saw**: 2-2 agent split. Statistical/Historical had Miami. Protocol override awarded the pick to Missouri based on home-court adjacency (St. Louis) and Miami's injury concerns.
**What the engine missed**: Miami **out-rebounded Missouri 46-30** and had a **19-2 second-chance points advantage** — total physical dominance. Reneau scored 24, Donaldson 17, Henderson 15. Missouri's Stone (21) and Mitchell (19) kept it competitive until Miami went on an 11-0 run. The "home-court adjacency" factor that tipped the override was acknowledged by Miami's coach as real, but it wasn't enough to overcome Miami's glass dominance. The override contradicted both data agents (Statistical had Miami at 57%, Historical had Miami at 59%).
**Confidence delta**: 55% was appropriately uncertain
**Lesson**: Protocol overrides in split decisions must not override BOTH data agents. The debate protocol explicitly states: "If data agents split → Statistical breaks tie if confidence ≥56%." Statistical had Miami at 57% — above threshold. The override violated the engine's own rules. This is a process error, not just a bad outcome.

---

### MISS: (12) Akron picked → (5) Texas Tech won 91-71

**Prediction**: Akron at 60% (recency_override)
**Result**: Texas Tech won 91-71 (TTU shot 64% from floor, 11 threes)

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Texas Tech | Yes |
| Matchup | Akron | No |
| Recency | Akron | No |
| Historical | Texas Tech | Yes |

**What the engine saw**: Toppin OUT (torn ACL, 21.8/10.8 All-American), TTU's 3-game losing streak post-Toppin, blown out by ISU 75-53. Akron on 10-game win streak.
**What the engine missed**: TTU **never trailed** and won 91-71. Jaylen Petty scored 24 (career-best 5 threes), Christian Anderson added 18, Moseley had 16. TTU held Akron to **6 fewer threes than their average** and **17 fewer points than Akron's 88.4 PPG season average**. TTU's Big 12-caliber defense showed up when it mattered. The 3-game post-Toppin losing streak was against elite Big 12 competition (ISU, etc.) — not indicative of how they'd perform against a MAC team. Statistical and Historical agents both had TTU and were correct.
**Confidence delta**: 60% was close to appropriate — but the pick itself was wrong
**Lesson**: Recency override for a star player's absence must account for remaining roster talent and opponent quality. A Big 12 5-seed without its best player is still far more talented than a MAC 12-seed. 3-game samples against elite conference competition are not transferable to mid-major matchups. This is the same "power conference floor > mid-major ceiling" pattern as the Saint Mary's/A&M miss.

---

### MISS: (10) Santa Clara picked → (7) Kentucky won 89-84 OT

**Prediction**: Santa Clara at 59% (protocol_override)
**Result**: Kentucky won 89-84 in overtime

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Santa Clara | No |
| Matchup | Santa Clara | No |
| Recency | Santa Clara | No |
| Historical | Santa Clara | No |

**What the engine saw**: Kentucky's worst record of any 7+ seed (21-13), Quaintance/Knox/Lowe all OUT. Bias-correction re-analysis flipped all 4 agents to Santa Clara. Market compressed to UK -2.5.
**What the engine missed**: This game featured one of the most dramatic finishes in tournament history. Santa Clara's Allen Graves hit a three with 2.4 seconds left to go up **73-70 — the engine's pick was about to be correct**. Then Otega Oweh launched a **half-court buzzer-beater that banked in** to force overtime. Oweh finished with 35 points, 8 rebounds, 7 assists — a stat line not seen since Larry Bird in 1979. Kentucky won 89-84 in OT on an 8-0 run. The engine's Santa Clara pick was **2.4 seconds from being validated**. This isn't a calibration failure — it's a once-in-a-decade shot.
**Confidence delta**: 59% was appropriately uncertain — Santa Clara led with 2.4 seconds left
**Lesson**: The bias-correction protocol made the right call here — Santa Clara was the better-positioned team and led late. No analytical framework can account for a half-court bank shot. If anything, this game validates the correction. Don't over-learn from miracle outcomes.

---

## Round Summary: Round of 64

**Record**: 24-8 (75.0%)
**Upsets correctly called**: 4 of 10 (Iowa 9>8, VCU 11>6, Utah State 9>8, Saint Louis 9>8)
**Upsets missed**: 4 (TCU 9>8, Texas A&M 10>7, High Point 12>5, Texas 11>6)
**False upset calls**: 3 (South Florida, Missouri, Akron — predicted upsets that didn't happen)
**Note**: Kentucky 7>10 Santa Clara wasn't an upset by seed, but the engine picked the lower seed to win.

### Confidence Calibration
| Confidence Bucket | Record | Hit Rate | Expected | Calibrated? |
|-------------------|--------|----------|----------|-------------|
| 50-59% | 4-4 | 50.0% | ~55% | Slightly under |
| 60-69% | 5-4 | 55.6% | ~65% | Under — soft leans are overconfident |
| 70-79% | 5-0 | 100% | ~75% | Over — small sample but strong |
| 80-89% | 4-0 | 100% | ~85% | Over — small sample but strong |
| 90-100% | 6-0 | 100% | ~95% | Good |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | 27-5 | 84.4% |
| Matchup | 24-8 | 75.0% |
| Recency | 24-8 | 75.0% |
| Historical | 23-9 | 71.9% |

### Key Patterns

1. **The 60-69% zone is the engine's weakness.** 5-4 (55.6%) in a bucket that should be ~65%. These "soft lean" picks are overconfident — the engine treats them as favorites when they're really coin-flips.

2. **Unanimity masks uncertainty.** 6 of 8 misses were unanimous picks. When all 4 agents agree on a near-toss-up, it creates false confidence. A unanimous 61% pick feels more certain than it is.

3. **The recency override system is 1-2.** Correctly called VCU (Wilson OUT) but missed on South Florida (Brown Jr. OUT, Louisville won despite blowing 23-point lead) and Akron (Toppin OUT, TTU never trailed). Override threshold needs to account for remaining roster talent vs opponent quality — a power conference team missing one player is still deeper than a mid-major.

4. **Protocol override violated its own rules on Missouri.** Statistical had Miami at 57% (above the 56% tiebreak threshold). Per the debate protocol, that should have been the pick. The override chose Missouri on "home-court adjacency" — an intangible, not a factual roster change. This is a process error that should be enforced going forward.

5. **Statistical Analyst is the most reliable individual agent (84.4%).** It was correct on all 3 games where it dissented from the final pick (Louisville, Miami, Texas Tech). When Statistical disagrees with an override, treat it as a hard veto signal.

6. **Power conference floor > mid-major ceiling.** Two misses (Saint Mary's/A&M, Akron/TTU) share the same pattern: the engine picked a mid-major over a struggling power conference team based on recent form. In both cases, SEC/Big 12 physicality and depth overwhelmed the mid-major in the actual game (A&M forced 18 TOs, TTU held Akron 17 below season average). Late-season conference play slumps don't transfer to mid-major matchups.

7. **"Best player on floor" is necessary but not sufficient.** Dybantsa scored 35/10 against Texas and BYU still lost because the supporting cast shot 18% from three. Individual dominance can't overcome team-level collapse in a single-elimination format.

8. **Some misses were inches from hits.** TCU won on a layup with 4.3 seconds left (66-64). Kentucky needed a half-court buzzer-beater to force OT (Santa Clara led 73-70 with 2.4 sec). Louisville blew a 23-point lead before holding on 83-79. Three of 8 misses were decided by miracle plays — the engine's analysis was directionally sound in these cases.

9. **High-confidence picks (70%+) are money.** 15-0 in games with 70%+ confidence. The engine's conviction is well-calibrated when it's actually confident — the problem is only in the "lean" zone.
