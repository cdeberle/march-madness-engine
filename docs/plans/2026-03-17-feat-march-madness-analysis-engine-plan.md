---
title: "feat: March Madness Agentic Analysis Engine"
type: feat
status: active
date: 2026-03-17
origin: docs/brainstorms/2026-03-17-march-madness-engine-brainstorm.md
---

# March Madness Agentic Analysis Engine

A Claude Code workflow that evaluates NCAA tournament matchups round-by-round using 4 specialist sub-agents. An orchestrator dispatches agents, synthesizes assessments through a data-first debate layer, and produces picks. User reviews and advances each round manually.

---

## Architecture

```
User provides bracket PDF → Reviews picks → Advances to next round
        │                          ▲
        ▼                          │
   ORCHESTRATOR (orchestrator.md)
   1. Extract/verify matchups from PDF (R1) or prior picks.json (R2+)
   2. Dispatch 4 agents per matchup (parallel, by region)
   3. Debate/consensus — data > intangibles, always
   4. Write analysis.md + picks.json → user reviews → next round (full reset)
        │
        ├── Statistical Analyst   (data — highest weight)
        ├── Matchup Analyst       (data — high weight)
        ├── Recency Analyst       (mixed — medium weight)
        └── Historical Analyst    (context — lowest weight)
```

## Agent Prompts

All in `agents/` as separate `.md` files.

| File | Domain |
|------|--------|
| `orchestrator.md` | Extraction, dispatch, synthesis, output |
| `statistical-analyst.md` | KenPom, NET, BPI, efficiency, SOS |
| `matchup-analyst.md` | Pace, shooting, turnovers, rebounding, scheme fit |
| `recency-analyst.md` | Last 5-10 games, injuries, roster availability |
| `historical-analyst.md` | Seed trends, program history, coach record |
| `schema.md` | Shared output contract for all agents |

Each agent returns: pick, confidence %, key factors, risk factors, sources, data gaps, upset flag.

**Confidence calibration** (included in each agent prompt):
- **90-100%**: Extreme mismatch
- **75-89%**: Clear favorite
- **60-74%**: Lean, meaningful uncertainty
- **50-59%**: Near toss-up

---

## Debate Protocol

**Data trumps intangibles — with one exception.**

- **Agents agree** — pick matches consensus, confidence = average.
- **Agents split** — data agents (Statistical, Matchup) outweigh context agents (Recency, Historical). If data agents agree, that's the pick. If data agents split, Statistical breaks the tie.
- **Recency override** — factual, material developments (player ruled out, suspension, injury, legal issues) override statistical projections. Season-long stats assume a full roster — if the roster changed, the stats are stale. Recency-as-vibes (momentum, "hot streak") stays low-weight.
- **Data gaps** — agent with missing data gets reduced weight. 2+ agents with material gaps = "Low Confidence" flag.

Report shows all 4 agent assessments. When agents disagree, the report explains the resolution.

---

## Output

Each round writes to `output/<round-name>/` (e.g., `output/round-of-64/`):

- **`analysis.md`** — head-to-head stat tables, all 4 agent assessments, final pick with confidence and deciding factor per matchup
- **`picks.json`** — structured data: winner, confidence, consensus type, upset flag, agent picks per matchup

## Round Advancement

Read prior round's `picks.json` → derive next matchups from bracket position → full context reset (new conversation, no carryover) → run next round.

---

## File Structure

```
march-madness-engine/
├── CLAUDE.md
├── agents/
│   ├── orchestrator.md
│   ├── statistical-analyst.md
│   ├── matchup-analyst.md
│   ├── recency-analyst.md
│   ├── historical-analyst.md
│   └── schema.md
├── data/
│   └── 2026 bracket.pdf
└── output/
    ├── round-of-64/
    ├── round-of-32/
    ├── sweet-16/
    ├── elite-8/
    ├── final-4/
    └── championship/
```
