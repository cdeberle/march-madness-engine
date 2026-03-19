# R64 Bias Correction — Cinderella Re-Analysis (2026-03-18)

## Context

After completing the Sweet 16, the bracket produced an all-chalk Elite 8 (all 1-seeds and 2-seeds). A tiebreaker bias review (see `2026-03-18-sweet-16-tiebreaker-review.md`) identified systemic favorite-lean in the protocol. The user then asked: what Cinderellas are experts backing that the engine dismissed?

Research identified three R64 matchups where expert consensus diverged significantly from engine picks:
1. **(6) UNC vs (11) VCU** — experts widely picking VCU for the Sweet 16
2. **(7) Kentucky vs (10) Santa Clara** — experts broadly picking Santa Clara outright
3. **(5) Wisconsin vs (12) High Point** — most-hyped Cinderella in the field

All three were re-analyzed with 4 agents each, using bias-corrected prompts that explicitly instructed agents to:
- Not over-weight SOS gaps between power and mid-major conferences
- Not give credit for "program pedigree" when the team is injured/depleted
- Evaluate the CURRENT team, not the brand
- Treat elite mid-major efficiency metrics as genuine, not schedule mirages

## Re-Analysis Results

### FLIP: R64 Game 13 — UNC (59%) → VCU (58%)

**Original:** UNC 59%, majority (3-1, Recency dissented)
**Re-analysis:** VCU 58%, majority (3-1, Historical dissented)

| Agent | Original | Re-analysis | Swing Factor |
|-------|----------|-------------|--------------|
| Statistical | UNC 58% | **VCU 54%** | Wilson OUT drops UNC scoring 8+ PPG; BPI at 61.6% no longer reflects current team |
| Matchup | UNC 62% | **VCU 62%** | Havoc press exploits UNC's ball-handler gap without Wilson; UNC last in ACC 3PT defense vs VCU's distributed shooting (all 8 rotation players hit 18+ threes) |
| Recency | VCU 55% | **VCU 62%** | UNC's 5 wins without Wilson were mostly against weak ACC opponents (Louisville only quality win); VCU 16-of-17 with conference double crown |
| Historical | UNC 61% | UNC 61% | 6-vs-11 historically ~39% upset rate; UNC SRS still superior. Only holdout. |

**Why the original was wrong:** The engine's original data agents treated Wilson's absence as "priced in" by BPI (61.6% UNC). But BPI measures the program's season-long profile — it doesn't fully discount a 19.8 PPG / 9.4 RPG player being OUT. The re-analysis with bias correction revealed that:
- UNC averaged only 71.8 PPG without Wilson (down 8 from 79.8)
- UNC's neutral/away record was 6-8 (tournament games are neutral site)
- VCU's Havoc scheme specifically targets teams with weakened ball-handling — exactly UNC's post-Wilson vulnerability
- Multiple experts and CBS models (37% VCU probability) aligned with the upset pick

### FLIP: R64 Game 31 — Kentucky (64%) → Santa Clara (59%)

**Original:** Kentucky 64%, unanimous (4-0)
**Re-analysis:** Santa Clara 59%, unanimous (4-0)

| Agent | Original | Re-analysis | Swing Factor |
|-------|----------|-------------|--------------|
| Statistical | Kentucky 64% | **Santa Clara 63%** | Kentucky NET #28 built with healthy roster; Quaintance confirmed OUT for opening weekend, Knox OUT, Lowe OUT. Santa Clara AdjEM #35, top-23 offense. |
| Matchup | Kentucky 64% | **Santa Clara 57%** | Santa Clara's 3PT volume (29.2 attempts/game) exploits depleted Kentucky interior without rim protector Quaintance. 7 of 9 rotation players shoot from deep. |
| Recency | Kentucky 64% | **Santa Clara 62%** | Quaintance confirmed OUT by Coach Pope (hasn't played since January 7, appeared in only 4 games all season). Knox OUT, Lowe OUT. Kentucky at 21-13 — worst record of any 7+ seed. Santa Clara 26-8, fully healthy, 3 All-WCC First Team players. |
| Historical | Kentucky 64% | **Santa Clara 54%** | 7-vs-10 historically ~39% upset rate. Kentucky 21-13 is historically anomalous for a 7-seed. Pope first year. Santa Clara first tournament since 1996 adds uncertainty. |

**Why the original was wrong:** This was the clearest case of brand-name bias. The original run produced a unanimous 64% for Kentucky — identical confidence from all four agents — which itself is suspicious (agents rarely converge to the same number unless anchoring on a prior). Kentucky at 21-13 with three rotation players OUT should never have been a 64% favorite. The re-analysis correctly identified that:
- Kentucky's efficiency metrics were built with a healthy roster that no longer exists
- Quaintance (their best player) hasn't played since January 7
- Santa Clara's offensive efficiency (#23 nationally) is genuinely elite
- SI explicitly noted Santa Clara "will be one of the most common upset picks in brackets"
- The market had compressed to Kentucky -2.5 to -3.5, signaling a near coin-flip

### HOLD: R64 Game 19 — Wisconsin (69%) over High Point

**Original:** Wisconsin 69%, unanimous
**Re-analysis:** Wisconsin ~69%, unanimous (no change)

| Agent | Original | Re-analysis | Swing Factor |
|-------|----------|-------------|--------------|
| Statistical | Wisconsin 72% | Wisconsin 74% | Wisconsin ORtg #7 vs HP defensive efficiency #161. NET gap 51 spots. |
| Matchup | Wisconsin 72% | Wisconsin 72% | Wisconsin TO rate 12.8% (#3) directly neutralizes HP's 21 PPG off turnovers. HP has no proven alternative. |
| Recency | Wisconsin 68% | Wisconsin 68% | HP 14-game streak is real. Wisconsin's Winter (ankle) day-to-day adds risk. |
| Historical | Wisconsin 62% | Wisconsin 62% | 5-vs-12 at ~35% upset rate. HP first tournament. Gard 7-7 in NCAAs. |

**Why it holds:** High Point is the most-hyped Cinderella in the field — but Wisconsin is the *wrong opponent* for their identity. HP's entire offense runs through turnover-generated transition (21 PPG off turnovers, #1 steal rate). Wisconsin's 12.8% TO rate (#3 nationally) is a direct, measurable counter. The Matchup analyst confirmed: if Wisconsin doesn't turn it over, HP must win a half-court efficiency battle where Wisconsin ranks #7 and HP's defense ranks #161. That's not a viable upset path.

**Monitoring flag:** If Nolan Winter (13.3/8.6, ankle) is confirmed OUT, this game tightens. His interior presence is critical to Wisconsin's rebounding and half-court defense.

## Cascade Analysis

### VCU flip — R32 impact

R32 South Game 7 changes from **(6) UNC vs (3) Illinois** to **(11) VCU vs (3) Illinois**.

Original: Illinois won 76% (unanimous). UNC was missing Wilson — a depleted opponent.

With VCU: **This game needs re-analysis.** VCU is a more dangerous stylistic matchup than depleted UNC:
- VCU's Havoc press generates exactly the turnover-driven chaos that can exploit Illinois's defensive weakness (~#28 nationally)
- Illinois's #1 AdjOE should still dominate in half-court, but VCU's pressure could prevent half-court sets from forming
- Illinois is still likely favored but confidence should drop — estimated 65-70% instead of 76%
- **If VCU wins R32:** Sweet 16 South becomes (1) Florida vs (11) VCU — the Cinderella run experts predicted

### Santa Clara flip — R32 impact

R32 Midwest Game 16 changes from **(7) Kentucky vs (2) Iowa State** to **(10) Santa Clara vs (2) Iowa State**.

Original: Iowa State won 81% (unanimous). Kentucky was badly depleted.

With Santa Clara: **Iowa State still wins at similar confidence (~78-81%).** ISU's pressure defense (21.9% TO force rate, #4) is effective against any opponent, and Santa Clara's 136th-ranked defense won't contain ISU's elite offense. Santa Clara's 3PT volume is their weapon but ISU holds opponents to 32.1% from deep. **No re-analysis needed — Iowa State advances.**

### High Point hold — no cascade

Wisconsin still wins. No downstream changes.

## Summary of All Changes

| Game | Round | Original | Override | Cascade |
|------|-------|----------|----------|---------|
| G13 | R64 | UNC 59% | **VCU 58%** | R32 G7 needs re-analysis (VCU vs Illinois) |
| G31 | R64 | Kentucky 64% | **Santa Clara 59%** | R32 G16 Iowa State still wins (~78-81%) |
| G19 | R64 | Wisconsin 69% | Wisconsin 69% (hold) | None |

## Files Modified
- `output/round-of-64/picks.json` — G13 and G31 flipped
- `output/round-of-32/picks.json` — G7 and G16 matchup participants updated
- This document

## Outstanding Re-Analysis Required
- **R32 South Game 7: (11) VCU vs (3) Illinois** — full 4-agent re-analysis needed before Sweet 16 results can be confirmed. If VCU wins, Sweet 16 South changes.
