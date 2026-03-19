# Elite 8 — COMPLETE

## Status
- **Games completed:** 4 / 4
- **Round complete.** Ready for Final Four analysis in a new session.

## All Picks

| Game | Region | Matchup | Pick | Confidence | Consensus | Upset? |
|------|--------|---------|------|------------|-----------|--------|
| 1 | East | (1) Duke vs (2) UConn | **Duke** | 64% | Unanimous | No |
| 2 | South | (1) Florida vs (2) Houston | **Houston** | 57% | Split (situational) | Yes |
| 3 | West | (1) Arizona vs (2) Purdue | **Arizona** | 66% | Unanimous | No |
| 4 | Midwest | (1) Michigan vs (2) Iowa State | **Michigan** | 62% | Majority (3-1) | No |

## Final Four Matchups (derived)
- **Semifinal 1:** (1) Duke vs (2) Houston
- **Semifinal 2:** (1) Arizona vs (1) Michigan

## Upsets Picked (Elite 8)
- Houston over Florida (2-seed over 1-seed, home court tiebreaker)

## Cumulative Upset Count
| Round | Upsets | Notable |
|-------|--------|---------|
| Round of 64 | 7 | USF, Utah State, Iowa, SLU, Missouri (override), Akron, VCU (bias correction), Santa Clara (bias correction) |
| Round of 32 | 3 | St. John's over Kansas, Vanderbilt over Nebraska, Akron over Alabama |
| Sweet 16 | 0 | All 1-seeds and 2-seeds advanced |
| Elite 8 | 1 | Houston over Florida (home court) |

## Protocol Changes Made This Session

### 1. Tiebreaker Threshold (codified in orchestrator.md)
When data agents split, the Statistical Analyst breaks the tie **only if confidence ≥ 56%.** Below that, the tiebreaker is void — pick goes to 3+ agent consensus, or factual situational factors break a 2-2 split.

**Impact this round:** Game 2 (Florida/Houston). Statistical at 54% was below threshold. Agents split 2-2. Home court (Toyota Center) broke the tie. Same outcome as old protocol, but better-justified reasoning.

### 2. Bias Corrections (added to statistical-analyst.md)
- Don't over-weight SOS gaps
- Don't credit brand-name pedigree for depleted rosters
- Seeding is not a signal (1v2 doesn't imply default favorite)
- Watch for anchoring

**Impact this round:** Minimal for Elite 8 specifically — all teams are power-conference 1/2-seeds. The "seeding is not a signal" instruction helped agents calibrate honestly (average confidence 62.3%, not inflated).

## Key Learnings

1. **1v2 matchups are genuinely close.** Average confidence 62.3% — lowest of any round. Historical base rate for 1-seeds in 1v2 E8 is only ~45-55%.

2. **Venue matters as a factual tiebreaker.** Houston at Toyota Center was the most concrete situational factor in the entire Elite 8.

3. **Injury carry-forward was accurate.** All projections from Sweet 16 handoff held.

4. **New injuries surfaced:**
   - Purdue's Jacobsen (7'4" C) season-ending (eliminated)
   - Michigan's Grady questionable (undisclosed) — monitor
   - UConn's Stewart (right knee) since Feb 21 (eliminated)
   - Arizona's Bradley wrist (negative X-ray) — monitoring

5. **Lloyd's 0-3 in regional semis** was independently identified by the Historical Analyst. Arizona broke through — if the pick holds, this pattern is broken.

## Injury Carry-Forward for Final Four

| Player | Team | Injury | Status | Notes |
|--------|------|--------|--------|-------|
| Caleb Foster | Duke | Broken foot (surgery) | OUT — season | Priced into metrics |
| Patrick Ngongba II | Duke | Right foot soreness | Day-to-day | Key swing factor. ~20+ days since boot (3/18). |
| L.J. Cason | Michigan | Torn ACL | OUT — season | Priced into metrics |
| Winters Grady | Michigan | Undisclosed | Questionable | NEW — monitor |
| Brayden Burries | Arizona | Quad/calf + illness | Day-to-day | Expected available |
| Jaden Bradley | Arizona | Wrist (negative X-ray) | Monitoring | Not serious |
| J'Wan Roberts | Houston | Grade 2 ankle (Mar 12) | Playing (managed) | Re-aggravation risk over 4+ games |

## Decision Docs
- `docs/decisions/2026-03-18-session-1-changelog.md`
- `docs/decisions/2026-03-18-sweet-16-tiebreaker-review.md`
- `docs/decisions/2026-03-18-r64-bias-correction.md`

## Resume Instructions
For Final Four: start a new session and say **"Begin analysis on final-4."** Read `output/elite-8/picks.json` to derive Final Four matchups.

**Before starting Final Four:**
1. Read this handoff for injury context and protocol state
2. Verify Duke Ngongba status (most important injury update — ~20 days post-boot by Final Four)
3. Verify Michigan Grady status
4. Verify Houston Roberts ankle status (cumulative wear over 4+ tournament games)
