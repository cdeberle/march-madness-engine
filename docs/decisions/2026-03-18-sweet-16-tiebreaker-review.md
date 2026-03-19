# Sweet 16 Tiebreaker Bias Review — Session 3 (2026-03-18)

## Context

After completing all 8 Sweet 16 games, the bracket produced an all-chalk result: all four 1-seeds and all four 2-seeds advanced to the Elite 8 — zero upsets. This was striking given the engine had picked 3 upsets in the Round of 64 and 3 in the Round of 32.

The user observed the pattern and asked for the likelihood (~1-2% historically for all 1s and all 2s to reach the Elite 8). This triggered a review of the debate protocol's tiebreaker mechanics and their systemic bias toward favorites.

## The Bias

**Root cause:** When data agents split, the Statistical Analyst breaks the tie. The Statistical Analyst weights AdjEM/NET most heavily — and higher seeds almost always win those metrics. This means the tiebreaker systematically favors the higher-ranked team regardless of:
- Matchup-specific scheme advantages
- Situational factors (home court, injuries, fatigue)
- Convergence of the other three agents

**Severity:** In the Sweet 16, data agents split in 3 of 8 games (37.5%). All three tiebreakers went to the higher seed. This is a structural bias, not coincidence.

## The Review

All 56 picks across R64, R32, and S16 were audited for:
1. Split decisions where Statistical tiebreaker fired
2. Sub-60% confidence picks (even if unanimous)
3. Cases where 3+ agents converged on the losing side of the tiebreak

### Criterion for override

A tiebreaker was overridden when:
- Statistical confidence was at or near minimum (50-57%)
- Three or more agents independently converged on the opposite pick
- A concrete situational or scheme-specific factor broke the tie more convincingly than the blunt efficiency comparison

A tiebreaker was **held** when:
- Statistical confidence was 62%+ (genuine conviction)
- The dissenting agent's case was speculative or depth-dependent on a single player

## Flips

### 1. S16 Game 2: Michigan State (54%) → UConn (57%)

| Factor | MSU Case | UConn Case |
|--------|----------|------------|
| Statistical | 52% (minimum conviction) | — |
| Agent convergence | 1 of 4 | 3 of 4 (Matchup 58%, Recency 62%, Historical 61%) |
| Scheme fit | Interior-heavy offense | Defense purpose-built to stop interior: top-10 block rate, 45.2% opp 2PT |
| Structural weakness | 321st 3PT defense | UConn shoots 35.2% from three |
| KenPom gap | ~#9 vs ~#12 | Below protocol's own <3 AdjEM low-confidence threshold |

**Decision:** Flipped. A 52% tiebreaker carries no conviction. Three converging agents with concrete scheme reasoning outweigh a coin-flip Statistical pick.

**Cascade:** Elite 8 East becomes **(1) Duke vs (2) UConn** instead of Duke vs Michigan State.

### 2. R64 Game 23: Miami (57%) → Missouri (55%)

| Factor | Miami Case | Missouri Case |
|--------|------------|---------------|
| Statistical | 57% (thin conviction) | — |
| Agent convergence | 2 of 4 (Statistical, Historical) | 2 of 4 (Matchup, Recency) |
| Situational | Injury concerns flagged | Home-court adjacency (game in St. Louis) |
| Scheme | Efficiency edge (ORtg 33rd vs 50th) | Matchup analyst identified specific advantages |

**Decision:** Flipped. True 2-2 split (not 3-1). Statistical at 57% is thin. Situational factors (home court, health) break the tie more reliably than a 5-point efficiency edge at this confidence level.

**Cascade:** R32 Game 12 becomes (10) Missouri vs (2) Purdue instead of Miami vs Purdue. Purdue won 69% unanimously — outcome unchanged. **No downstream impact.**

## Holds (Flagged as Close)

### S16 Game 3: Florida (62%) over Vanderbilt — HELD

Statistical at 63% has genuine conviction. Three of four agents picked Florida. The SEC Tournament blowout (91-74 Vandy win, 4 days prior) is alarming but: season series split 1-1, Florida's turnover spike was a statistical outlier, and Vandy's 133rd-ranked defense is a structural liability.

**Why it's flagged:** Vanderbilt is KenPom #12 as a 5-seed (most under-seeded team in the field). Multiple analysts called them "screwed on seeding." The Matchup analyst built a concrete offensive scheme case. If the SEC Tournament game is treated as *signal* rather than *noise*, this flips. **Most likely pick to be wrong if re-analyzed.**

### S16 Game 6: Purdue (63%) over Gonzaga — HELD

Statistical at 64% with 3-of-4 agent agreement. Purdue 4-0 all-time vs Gonzaga, all by double digits. Huff OUT collapses Gonzaga's interior depth to one player (Ike) — no backup if he fouls out. The Matchup dissent (Ike vs Purdue's 342nd rim defense) is legitimate but fragile.

### R32 Game 10: Arkansas (57%) over Wisconsin — HELD

Statistical at 62% has real conviction. Arkansas KenPom #15 vs Wisconsin #22, Acuff is the best player on the floor, SEC Tournament champions. Wisconsin's 3PT rate (42.5%, #4) exploiting Arkansas's porous defense is the Matchup counter, but the efficiency gap is meaningful.

## Picks Not Flagged (thin but unanimous)

| Round | Game | Pick | Conf. | Why safe |
|-------|------|------|-------|----------|
| R64 | 10 | Iowa over Clemson | 56% | Unanimous. Clemson lost 2 ACL players. |
| R32 | 2 | St. John's over Kansas | 60% | Unanimous. All metrics favored SJU. |
| R32 | 6 | Vanderbilt over Nebraska | 59% | Unanimous. BPI + ORtg edge clear. |
| R32 | 14 | Akron over Alabama | 56% | Recency override. Holloway suspended. |

## Updated Bracket State

### Files Modified
- `output/round-of-64/picks.json` — Game 23: Miami → Missouri (protocol_override)
- `output/round-of-32/picks.json` — Game 12: Miami → Missouri in matchup (Purdue still wins)
- `output/sweet-16/picks.json` — Game 2: Michigan State → UConn (protocol_override)
- `output/sweet-16/analysis.md` — Game 2 writeup updated
- `output/sweet-16/checkpoint.json` — Game 2 winner updated
- `output/sweet-16/HANDOFF.md` — Reflects UConn, documents override

### Elite 8 Matchups (Final)
- **East:** (1) Duke vs (2) UConn *(changed from Duke vs MSU)*
- **South:** (1) Florida vs (2) Houston
- **West:** (1) Arizona vs (2) Purdue
- **Midwest:** (1) Michigan vs (2) Iowa State

### Upset Count by Round (Final)
| Round | Upsets | Notable |
|-------|--------|---------|
| Round of 64 | 5 | USF over Louisville (recency), Utah State over Villanova, Iowa over Clemson, SLU over Georgia, **Missouri over Miami (override)**, Akron over Texas Tech (recency) |
| Round of 32 | 3 | St. John's over Kansas, Vanderbilt over Nebraska, Akron over Alabama (recency) |
| Sweet 16 | 0 | All 1-seeds and 2-seeds advance |

*Note: R64 upset count increased from 4 to 5 with the Missouri flip.*

## Recommended Protocol Change

**Add a minimum confidence threshold for Statistical tiebreaker:**

> When data agents split and the Statistical Analyst's confidence is below 56%, the tiebreaker is void. Instead, the pick goes to whichever side has 3+ total agents in agreement. If it remains 2-2, situational factors (home court, injuries, recent form) break the tie.

This preserves the Statistical tiebreaker when it has conviction (62%+ picks were all defensible) while preventing coin-flip picks from overriding agent consensus.

**Not yet codified** in orchestrator.md — should be added before Elite 8 analysis begins.

---

## Addendum: R64 Bias Correction (same session)

A follow-up analysis identified additional bias in R64 picks — specifically brand-name bias and SOS over-weighting against mid-majors. Two R64 games were flipped after full 4-agent re-analysis with bias-corrected prompts:
- **R64 G13:** UNC → VCU (Wilson OUT + Havoc scheme advantage)
- **R64 G31:** Kentucky → Santa Clara (3 players OUT + brand-name bias)

One R32 game is flagged for re-analysis:
- **R32 G7:** VCU vs Illinois (replaces UNC vs Illinois) — VCU's Havoc press is a more dangerous stylistic matchup

Full details: `docs/decisions/2026-03-18-r64-bias-correction.md`
