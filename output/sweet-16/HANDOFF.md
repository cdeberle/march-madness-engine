# Sweet 16 — COMPLETE

## Status
- **Games completed:** 8 / 8
- **Round complete.** Ready for Elite 8 analysis in a new session.

## All Picks

| Game | Region | Matchup | Pick | Confidence | Consensus | Upset? |
|------|--------|---------|------|------------|-----------|--------|
| 1 | East | (1) Duke vs (5) St. John's | **Duke** | 72% | Unanimous | No |
| 2 | East | (3) Michigan State vs (2) UConn | **UConn** | 57% | Protocol override | No |
| 3 | South | (1) Florida vs (5) Vanderbilt | **Florida** | 62% | Split (Statistical tiebreak) | No |
| 4 | South | (3) Illinois vs (2) Houston | **Houston** | 65% | Unanimous | No |
| 5 | West | (1) Arizona vs (4) Arkansas | **Arizona** | 68% | Unanimous | No |
| 6 | West | (3) Gonzaga vs (2) Purdue | **Purdue** | 63% | Split (Statistical tiebreak) | No |
| 7 | Midwest | (1) Michigan vs (12) Akron | **Michigan** | 81% | Unanimous | No |
| 8 | Midwest | (3) Virginia vs (2) Iowa State | **Iowa State** | 67% | Unanimous | No |

## Elite 8 Matchups (derived)
- **East:** (1) Duke vs (2) UConn
- **South:** (1) Florida vs (2) Houston
- **West:** (1) Arizona vs (2) Purdue
- **Midwest:** (1) Michigan vs (2) Iowa State

## Upsets Picked (Sweet 16)
- None. All higher seeds or equal seeds advanced.

## R64/R32 Bias-Correction Flips (approved this session)
After identifying tiebreaker bias and mid-major dismissal patterns, the following earlier-round picks were corrected:

| Round | Game | Original | Corrected | Cascade |
|-------|------|----------|-----------|---------|
| R64 G23 | Miami vs Missouri | Miami 57% | **Missouri 55%** | Purdue still wins R32 |
| R64 G13 | UNC vs VCU | UNC 59% | **VCU 58%** | Illinois wins R32 at 64% (was 76% vs UNC) |
| R64 G31 | Kentucky vs Santa Clara | Kentucky 64% | **Santa Clara 59%** | Iowa State wins R32 at 79% |

Total upset count across all rounds:
- **R64:** 7 upsets (USF, Utah State, Iowa, SLU, Missouri, Akron, VCU, Santa Clara) — *increased from 5 to 7*
- **R32:** 3 upsets (St. John's, Vanderbilt, Akron)
- **S16:** 0 upsets

## Protocol Overrides & Corrections
1. **S16 G2:** MSU→UConn (tiebreaker at 52% lacked conviction, 3/4 agents favored UConn)
2. **R64 G23:** Miami→Missouri (2-2 split, home-court + injury situational factors)
3. **R64 G13:** UNC→VCU (bias-corrected re-analysis, Wilson OUT + Havoc scheme, 3/4 agents flipped)
4. **R64 G31:** Kentucky→Santa Clara (bias-corrected re-analysis, 3 players OUT, unanimous 4/4 flip)
5. **R32 G7:** UNC→VCU in matchup, Illinois re-analyzed at 64% (was 76% vs UNC)
6. **R32 G16:** Kentucky→Santa Clara in matchup, Iowa State adjusted to 79% (was 81%)

## Key Learnings

1. **Tiebreaker bias:** Statistical tiebreaker systematically favors higher seeds. Recommended 56% minimum threshold. See `docs/decisions/2026-03-18-sweet-16-tiebreaker-review.md`.

2. **Mid-major dismissal bias:** Engine over-weighted SOS gaps and under-valued mid-major efficiency metrics. VCU and Santa Clara were both expert consensus upset picks that the engine dismissed. See `docs/decisions/2026-03-18-r64-bias-correction.md`.

3. **Brand-name bias:** Kentucky at 21-13 with 3 players OUT got unanimous 64% — identical from all 4 agents (anchoring signal). Re-analysis flipped it unanimously to Santa Clara.

4. **Illinois deep dive findings (relevant for S16 analysis):**
   - Illinois 0-4 in OT, 5-5 in last 10 — but Boswell (hand) and Stojakovic (ankle) both missed significant time during that stretch and are now cleared
   - Wagler's 2.4 AST/TO ratio makes Illinois a poor Havoc victim
   - Illinois's dead-last forced TO rate means opponents get clean half-court looks
   - VCU's 2026 Havoc is a refined version (~17 forced TO/game vs Smart's ~22) with better offensive balance

5. **Injury carry-forward for Elite 8:** Duke Foster OUT, Ngongba day-to-day; Gonzaga Huff OUT (eliminated); Arkansas Knox OUT (eliminated); Michigan Cason OUT (ACL); Arizona Burries day-to-day; ISU Lipsey groin trending positive.

## Decision Docs
- `docs/decisions/2026-03-18-session-1-changelog.md` — Agent config, prompt engineering, source audit
- `docs/decisions/2026-03-18-sweet-16-tiebreaker-review.md` — Tiebreaker bias analysis, S16 flips, protocol recommendation
- `docs/decisions/2026-03-18-r64-bias-correction.md` — Cinderella re-analysis, R64 flips, cascade analysis

## Resume Instructions
For Elite 8: start a new session and say **"Begin analysis on elite-8."** Read `output/sweet-16/picks.json` to derive Elite 8 matchups.

**Before starting Elite 8:**
1. Read all three decision docs above for protocol learnings
2. Codify the 56% minimum-confidence threshold into `agents/orchestrator.md`
3. Add bias-correction instructions to agent prompts: do not over-weight SOS, do not credit brand-name pedigree for depleted rosters
