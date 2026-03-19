---
date: 2026-03-17
topic: march-madness-analysis-engine
---

# March Madness Agentic Analysis Engine

## What We're Building

A Claude Code-driven March Madness bracket analysis engine that evaluates each tournament round independently using specialist sub-agents. An orchestrator dispatches research agents to analyze matchups from multiple angles, then synthesizes their findings through a debate/consensus layer to produce statistically-justified picks. The user maintains full control between rounds — reviewing, overriding, and triggering each successive round.

## Why This Approach

- **Orchestrator + specialists** gives depth without losing coherence — each agent focuses on one analytical lens
- **Debate layer** surfaces conflicting signals transparently instead of hiding uncertainty
- **Round-by-round reset** prevents narrative bias from contaminating later rounds
- **Claude Code scripts + prompts** keeps it lightweight (hobby project, not a production service)
- **PDF bracket + live web research** balances ground truth with real-time data

## Architecture

```
User provides PDF bracket
        │
        ▼
   Orchestrator (master prompt)
        │
        ├── Round N: Extract matchups
        │         │
        │         ▼
        │   For each matchup, dispatch 4 specialist agents in parallel:
        │     ├── Statistical Analyst (KenPom, NET, BPI, efficiency)
        │     ├── Stylistic/Matchup Analyst (pace, shooting, defensive schemes)
        │     ├── Recency/Intangibles Analyst (injuries, form, momentum)
        │     └── Historical Trends Analyst (seed performance, upset patterns)
        │         │
        │         ▼
        │   Debate/Consensus Layer
        │     - Each agent presents independent assessment
        │     - Orchestrator synthesizes, resolves conflicts
        │     - Produces pick with confidence + reasoning
        │         │
        │         ▼
        │   Output: Markdown report + JSON bracket data
        │         │
        │         ▼
        │   Human review → approve / override picks
        │         │
        │         ▼
        └── Next round (full reset, no carryover)
```

## Data Strategy

- **Ground truth:** User-provided PDF of the current bracket
- **Live research:** Web search for current stats, injury reports, recent form
- **No hallucinated stats:** Agents must cite sources or flag uncertainty

## Output Per Round

1. **Markdown report** — full matchup analyses with head-to-head breakdowns, key edges, confidence levels, upset flags
2. **JSON bracket data** — structured picks for tracking/feeding into bracket tools

## Key Decisions

- **Separate agent prompts:** Each sub-agent has its own `.md` file in `agents/`
- **No framework/SDK:** Pure Claude Code workflow with scripts and prompts
- **Full HITL:** User reviews and confirms before each round advances
- **Statistical rigor enforced:** Every pick must be data-justified; narrative-only picks are rejected
- **Conflict transparency:** When agents disagree, the final report explains the resolution

## File Structure

```
march-madness-engine/
├── CLAUDE.md                          # Project instructions for Claude Code
├── agents/
│   ├── orchestrator.md                # Master analysis prompt
│   ├── statistical-analyst.md         # KenPom, NET, BPI, efficiency metrics
│   ├── matchup-analyst.md             # Stylistic/scheme compatibility
│   ├── recency-analyst.md             # Injuries, recent form, intangibles
│   └── historical-analyst.md          # Seed trends, upset patterns, tournament history
├── data/
│   └── bracket.pdf                    # User-provided bracket (input)
├── output/
│   ├── round-of-64/
│   │   ├── analysis.md                # Full matchup report
│   │   └── picks.json                 # Structured bracket picks
│   ├── round-of-32/
│   ├── sweet-16/
│   ├── elite-8/
│   ├── final-4/
│   └── championship/
└── docs/
    └── brainstorms/
        └── 2026-03-17-march-madness-engine-brainstorm.md
```

## Next Steps

→ Write the agent prompt files
→ Build the orchestrator workflow
→ User provides bracket PDF to kick off Round of 64

---

## Addendum: Changes Made During Implementation

The following intentional changes were made after this brainstorm during planning and implementation:

- **Override workflow removed.** The brainstorm described a formal override flow (user edits `picks.json`). This was cut for simplicity — the user reviews picks and approves, but there's no structured override mechanism. Can be added later if needed.
- **Debate protocol: data > intangibles.** The brainstorm described the debate layer generically ("orchestrator synthesizes, resolves conflicts"). During planning, we formalized a strict hierarchy: Statistical and Matchup agents (data-tier) outweigh Recency and Historical agents (context-tier). Statistical breaks ties between data agents.
- **Recency override for roster changes.** Added a carve-out: factual, material roster changes (injury, suspension, legal issues) override statistical projections because season-long stats assume a full roster. "Momentum" and "vibes" remain low-weight.
- **`agents/schema.md` added.** A shared JSON output contract for all agents — not in the original brainstorm file structure but necessary for the debate layer to function reliably.
- **Agent weight tiers made explicit.** Each agent prompt now states its weight in the debate layer so agents can calibrate confidence appropriately.
- **Context reset = new conversation.** The brainstorm said "full reset, no carryover" — during implementation this was made concrete: each round runs in a new Claude Code conversation to prevent prior-round context from bleeding through.
- **Dispatch mechanism specified.** Agents are dispatched via Claude Code's Agent tool in parallel, processed by region (up to 8 matchups at a time).
