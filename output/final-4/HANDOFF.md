# Final Four — COMPLETE

## Status
- **Games completed:** 2 / 2
- **Round complete.** Ready for Championship analysis in a new session.

## All Picks

| Game | Matchup | Pick | Confidence | Consensus | Upset? |
|------|---------|------|------------|-----------|--------|
| 1 | (1) Duke vs (2) Houston | **Duke** | 61% | Majority (3-1) | No |
| 2 | (1) Arizona vs (1) Michigan | **Arizona** | 57% | Split (situational) | No |

## Championship Matchup (derived)
- **(1) Duke vs (1) Arizona**

## Upsets Picked (Final Four)
- None

## Cumulative Upset Count
| Round | Upsets | Notable |
|-------|--------|---------|
| Round of 64 | 7 | USF, Utah State, Iowa, SLU, Missouri (override), Akron, VCU (bias correction), Santa Clara (bias correction) |
| Round of 32 | 3 | St. John's over Kansas, Vanderbilt over Nebraska, Akron over Alabama |
| Sweet 16 | 0 | All 1-seeds and 2-seeds advanced |
| Elite 8 | 1 | Houston over Florida (home court) |
| Final Four | 0 | No upsets |

## Injury Carry-Forward for Championship

| Player | Team | Injury | Status | Notes |
|--------|------|--------|--------|-------|
| Caleb Foster | Duke | Broken foot (surgery) | OUT — season | Priced into metrics. Possible return rumored but unconfirmed. |
| Patrick Ngongba II | Duke | Right foot soreness | Day-to-day | Was OUT for R64. No confirmed Final Four update. ~20+ days post-boot. HIGH PRIORITY to verify. |
| Brayden Burries | Arizona | Quad/calf + illness | Day-to-day (playing) | Scored 21 in Big 12 title game. Airballed 3s earlier in tourney. Effectiveness variable. |
| Jaden Bradley | Arizona | Wrist (negative X-ray) | Available | Played through Big 12 championship. Not serious. |

## Key Learnings

1. **Final Four margins are razor-thin.** Average confidence 59% — lowest of any round. Both games featured AdjEM gaps of 5 points or less.

2. **Roster availability was decisive in Game 2.** Arizona and Michigan were statistically identical (AdjEM gap < 0.1). Michigan missing Grady and Cason (both OUT for season) was the tiebreaker in a 2-2 agent split.

3. **Houston's 2025 Final Four win over Duke was noted but did not override data.** Historical Analyst cited the precedent, but both data-tier agents agreed on Duke, making it a majority pick per protocol.

4. **The tiebreaker threshold (56%) worked as designed.** Game 2 had Statistical at 54% — below threshold. Tiebreaker voided, went to situational factors. Clean application of the protocol from the Elite 8 review.

5. **Ngongba (Duke) remains the biggest unknown.** His availability could materially shift Duke's championship projection. Must verify before championship analysis.

## Protocol State
- Tiebreaker threshold: 56% (codified in orchestrator.md)
- Bias corrections: active in statistical-analyst.md
- No new protocol changes this session

## Decision Docs
- `docs/decisions/2026-03-18-session-1-changelog.md`
- `docs/decisions/2026-03-18-sweet-16-tiebreaker-review.md`
- `docs/decisions/2026-03-18-r64-bias-correction.md`

## Resume Instructions
For Championship: start a new session and say **"Begin analysis on championship."** Read `output/final-4/picks.json` to derive the championship matchup.

**Before starting Championship:**
1. Read this handoff for injury context and protocol state
2. Verify Duke Ngongba status (most important injury update)
3. Verify Arizona Burries quad/calf status
4. Check if Caleb Foster (Duke) has actually returned
