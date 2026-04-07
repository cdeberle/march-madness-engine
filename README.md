# March Madness Analysis Engine v2026

A multi-agent bracket analysis framework built entirely in Claude Code. Four specialist AI analysts independently research every NCAA tournament matchup, then a structured debate protocol synthesizes their findings into statistically-justified picks — with explicit rules designed to minimize the biases that plague both human and AI bracket predictions.

## How It Works

The engine runs as a conversation-driven workflow in Claude Code. There is no application code, no framework, no SDK — just prompt files, a debate protocol, and structured output.

```
User provides bracket PDF
        |
        v
  Orchestrator reads matchups, presents for verification
        |
        v
  For each game, dispatch 4 specialist agents in parallel:
    |-- Statistical Analyst (AdjEM, NET, BPI, efficiency metrics)
    |-- Matchup Analyst (pace, scheme fit, stylistic interactions)
    |-- Recency Analyst (injuries, recent form, situational factors)
    |-- Historical Analyst (seed trends, coaching records, program pedigree)
        |
        v
  Each agent independently researches via web search and returns structured JSON
        |
        v
  Debate protocol resolves conflicts using a tiered weighting system
        |
        v
  Output: picks.json (structured) + analysis.md (writeup) per round
        |
        v
  Human reviews picks, triggers next round
        |
        v
  Full context reset between rounds (new conversation, no carryover)
```

Each agent runs as a Claude Code sub-agent (Sonnet model) with web search access, capped at 5-8 searches per dispatch to control cost. Agents return structured JSON per a shared schema (`agents/schema.md`), making their outputs machine-parseable for the debate layer.

## The Debate Protocol

The core design principle: **data outweighs narrative, with one exception.**

### Agent Tiers

Agents are explicitly told their weight in the debate layer so they calibrate confidence accordingly:

| Tier | Agent | Weight | Role |
|------|-------|--------|------|
| Data | Statistical Analyst | Highest | Efficiency metrics, rankings, resume quality |
| Data | Matchup Analyst | Second | Scheme fit, stylistic interactions, pace |
| Context | Recency Analyst | Medium | Injuries, form, situational factors |
| Context | Historical Analyst | Lowest | Seed trends, coaching records, program history |

### Resolution Rules

1. **All agents agree** — pick matches consensus. Confidence = average of all four.
2. **Agents split** — data agents (Statistical + Matchup) outweigh context agents (Recency + Historical). If both data agents agree, that's the pick.
3. **Data agents split** — the Statistical Analyst breaks the tie, **but only if its confidence is 56% or higher.** Below 56%, the tiebreaker is void.
4. **Tiebreaker void (2-2 split, no Statistical conviction)** — factual situational factors break the tie: confirmed injuries, venue advantage, roster availability. Not "momentum" or "vibes."
5. **Recency override** — confirmed, material roster changes (player ruled out, suspended) override all statistical projections, because season-long metrics assume a full roster.

### The 56% Threshold

This was the most important protocol refinement, added after the Sweet 16 produced an all-chalk Elite 8. A bias review revealed that when data agents split, the Statistical Analyst's tiebreaker systematically favored the higher-seeded team — because higher seeds almost always win efficiency metrics. At low confidence (50-55%), this is indistinguishable from a coin flip, but the protocol was treating it as decisive.

The fix: require minimum conviction. Below 56%, the tiebreaker is void and the protocol falls through to situational factors. This preserved the tiebreaker when it had real signal (62%+ picks were all defensible) while preventing coin-flip picks from overriding agent consensus.

This threshold directly affected 4 games in the tournament, including both Final Four semifinal picks and the national championship.

## Bias Elimination

The framework was designed around a specific problem: bracket predictions — whether by humans or AI — are riddled with systematic biases. The engine addresses each one through structural rules rather than hoping the AI "knows better."

### Brand-Name Bias

**Problem:** Humans (and LLMs trained on human text) over-weight program prestige. Kentucky "feels like" a tournament team even at 21-13 with three players out.

**Solution:** Agent prompts include explicit bias corrections:
- "Do not credit brand-name pedigree for depleted rosters"
- "Seeding is not a signal — a 1-seed vs 2-seed does not imply a default favorite"
- "Evaluate the current team, not the brand"

**Test case:** The engine initially picked Kentucky (7) over Santa Clara (10) at an identical 64% from all four agents — a telltale anchoring signal. After bias-corrected re-analysis, all four agents flipped to Santa Clara. Kentucky was 21-13 with their best player out since January.

### Favorite-Lean / Chalk Bias

**Problem:** Efficiency metrics favor higher seeds by definition (that's how seeds are assigned). Using efficiency as the primary tiebreaker creates a structural lean toward favorites in every close game.

**Solution:** The 56% confidence threshold prevents weak Statistical leans from deciding games. When the numbers say "this is basically a coin flip," the protocol acknowledges it and looks for concrete differentiators instead of pretending a 52% confidence pick is meaningful.

**Test case:** The Sweet 16 initially produced zero upsets (all 1-seeds and 2-seeds advanced). A protocol audit found that 3 of 8 games had data-agent splits resolved by thin Statistical tiebreakers. One was flipped (Michigan State → UConn), and the threshold was codified for all subsequent rounds.

### Strength-of-Schedule Over-Weighting

**Problem:** Mid-major teams with elite efficiency metrics get dismissed because they played a "weak schedule." But a team with top-40 AdjEM is genuinely good — SOS explains *why* their win total is high, not *whether* they're good.

**Solution:** Agent prompts include: "Do not over-weight Strength of Schedule gaps. A mid-major with elite efficiency metrics (top-40 AdjEM) is genuinely good." The debate protocol treats efficiency metrics as the primary signal, not SOS-adjusted resume.

### Narrative / Momentum Bias

**Problem:** "They're on a hot streak" and "they looked great last week" are not predictive signals, but they dominate human bracket reasoning.

**Solution:** The Recency Analyst's role is explicitly scoped to **facts about current state**, not narratives. Its prompt states: "'Momentum,' 'hot streak,' or 'they looked good last week' are NOT grounds for override." Only confirmed roster changes (injury, suspension, legal issues) can trigger an override — because these are facts that invalidate the statistical baseline, not vibes.

### Anchoring

**Problem:** When multiple agents produce suspiciously identical confidence numbers, they may be anchoring on shared priors (seeding, public consensus) rather than deriving independent assessments.

**Solution:** The Statistical Analyst's prompt includes: "Watch for anchoring. If your confidence matches another agent's exactly, you may be anchoring on shared priors. Derive your number independently from the metrics."

**Test case:** The original Kentucky-Santa Clara analysis produced 64% from all four agents — identical numbers from agents that should disagree. This was flagged as an anchoring signal and triggered re-analysis.

### Round-to-Round Contamination

**Problem:** A team that "looked impressive" in Round 1 gets inflated projections in Round 2, even though the opponent and context are completely different.

**Solution:** Each round runs in a **new Claude Code conversation** with a full context reset. The only carryover is the prior round's `picks.json` (to derive matchups) and `HANDOFF.md` (for injury status and protocol state). No prior-round narratives, agent outputs, or analysis carry forward.

## Project Structure

```
march-madness-engine/
├── CLAUDE.md                              # Project rules for Claude Code
├── README.md                              # This file
├── agents/
│   ├── orchestrator.md                    # Master workflow and debate protocol
│   ├── statistical-analyst.md             # Efficiency metrics, rankings, resume
│   ├── matchup-analyst.md                 # Scheme fit, pace, stylistic dynamics
│   ├── recency-analyst.md                 # Injuries, form, situational factors
│   ├── historical-analyst.md              # Seed trends, coaching, program history
│   └── schema.md                          # Shared JSON output contract
├── data/
│   └── bracket 2026.pdf                   # Input bracket (ESPN Tournament Challenge)
├── output/
│   ├── round-of-64/                       # picks.json, analysis.md, checkpoint.json, HANDOFF.md
│   ├── round-of-32/
│   ├── sweet-16/
│   ├── elite-8/
│   ├── final-4/
│   ├── championship/
│   ├── bracket.md                         # Full bracket reference (all 63 picks)
│   └── claude's completed bracket 2026.pdf
└── docs/
    ├── brainstorms/
    │   └── 2026-03-17-march-madness-engine-brainstorm.md
    ├── decisions/
    │   ├── 2026-03-18-session-1-changelog.md       # Engineering decisions
    │   ├── 2026-03-18-sweet-16-tiebreaker-review.md # Protocol bias audit
    │   └── 2026-03-18-r64-bias-correction.md        # Brand-name bias corrections
    └── plans/
        └── 2026-03-17-feat-march-madness-analysis-engine-plan.md
```

### Key Engineering Decisions

- **Sonnet for sub-agents:** 5-10x cheaper than Opus with sufficient research and JSON output quality.
- **5-8 search cap per agent:** Without this, agents made 30-60 searches and consumed 3-5x more tokens. The cap dropped per-game cost from ~5% to ~3% of context with no quality loss.
- **Foreground-only execution:** All agents run in foreground so their work is visible and monitorable in real time.
- **Blocked source documentation:** KenPom (paywall), Barttorvik (bot-blocked), The Athletic (paywall), and Warren Nolan (403) are explicitly listed as blocked in every agent prompt, with documented fallbacks.
- **Incremental checkpointing:** Results are written to disk after every single game. Token exhaustion mid-session loses only the current game, not the entire round.

## 2026 Results

**Predicted champion:** Duke (1-seed, East)
**Tiebreaker:** 143 total points (Duke 74, Arizona 69)
**Total upsets picked:** 11 across 63 games
**Average confidence:** ~68% overall, decaying from 74% (R64) to 58% (Championship)

| Round | Games | Upsets | Avg Confidence |
|-------|-------|--------|----------------|
| Round of 64 | 32 | 7 | 74% |
| Round of 32 | 16 | 3 | 69% |
| Sweet 16 | 8 | 0 | 67% |
| Elite 8 | 4 | 1 | 62% |
| Final Four | 2 | 0 | 59% |
| Championship | 1 | 0 | 58% |

## Limitations

- **Data freshness:** Agents rely on web search results available at analysis time. Injury reports change hourly during tournament week. A player ruled "questionable" on Tuesday may be confirmed out by Thursday tip-off.
- **Source accessibility:** KenPom and Barttorvik — the two best public analytics sources — are inaccessible to agents (paywall and bot-block respectively). ESPN BPI and EvanMiya are reasonable substitutes but less granular.
- **Single-game variance:** Basketball has high single-game variance. A 58% confidence pick means the other team wins 42% of the time. The engine is calibrated for honesty, not certainty.
- **No play-in analysis:** First Four play-in games were not independently analyzed. Play-in winners were slotted into the bracket after the fact. One game (Tennessee vs Miami OH) was initially analyzed against the wrong opponent (SMU) and had to be corrected.
- **AI reasoning biases:** Despite structural safeguards, LLMs still carry training-data biases. The bias correction system caught and fixed several cases (Kentucky, UNC, favorite-lean in tiebreakers) but likely didn't catch all of them.
