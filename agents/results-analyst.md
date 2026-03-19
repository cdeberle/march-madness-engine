# Results Analyst Protocol

## Purpose

Post-game and post-round analysis comparing engine predictions against actual tournament results. Identifies where the engine got it right, where it missed, and why.

## When to Run

- **After individual games**: User reports a result — log it immediately
- **After a round completes**: Full round retrospective with aggregate stats

## Process

### Step 1: Load Predictions

Read `output/<round-name>/picks.json` for the round being analyzed.

### Step 2: Record Results

For each reported result, create or update `output/<round-name>/results.json`:

```json
{
  "round": "round-of-64",
  "last_updated": "YYYY-MM-DD",
  "results": [
    {
      "game_number": 2,
      "region": "East",
      "team_a": { "name": "Ohio State", "seed": 8 },
      "team_b": { "name": "TCU", "seed": 9 },
      "predicted_winner": "Ohio State",
      "actual_winner": "TCU",
      "correct": false,
      "predicted_confidence_pct": 61,
      "consensus_type": "unanimous",
      "upset_occurred": true,
      "upset_predicted": false,
      "agent_picks": {
        "statistical": { "pick": "Ohio State", "correct": false },
        "matchup": { "pick": "Ohio State", "correct": false },
        "recency": { "pick": "Ohio State", "correct": false },
        "historical": { "pick": "Ohio State", "correct": false }
      }
    }
  ]
}
```

### Step 3: Generate Retrospective

Append to `output/<round-name>/retrospective.md`:

#### Per-Game Miss Entry

For every incorrect pick, document:

```markdown
### MISS: (seed) Predicted Winner vs (seed) Actual Winner

**Prediction**: [Winner] at [confidence]% ([consensus_type])
**Result**: [Actual winner] won

**Agent Breakdown**:
| Agent | Pick | Correct |
|-------|------|---------|
| Statistical | Team | Yes/No |
| Matchup | Team | Yes/No |
| Recency | Team | Yes/No |
| Historical | Team | Yes/No |

**What the engine saw**: [Key factors from the original analysis that supported the pick]
**What the engine missed**: [Risk factors from the original analysis that actually materialized]
**Confidence delta**: [confidence]% confidence was [too high / appropriately uncertain]
**Lesson**: [One-line takeaway for future calibration]
```

#### Per-Game Hit Entry (brief)

```markdown
### HIT: (seed) Winner over (seed) Loser — [confidence]% confidence
Consensus: [type] | All agents correct: [yes/no]
```

### Step 4: Round Summary (when round is complete)

At the end of the retrospective, generate an aggregate summary:

```markdown
## Round Summary: [round-name]

**Record**: X-Y (Z%)
**Upsets correctly called**: A of B
**Upsets missed**: C
**False upset calls**: D (predicted upset that didn't happen)

### Confidence Calibration
| Confidence Bucket | Record | Expected | Calibrated? |
|-------------------|--------|----------|-------------|
| 50-59% | X-Y | ~55% | Over/Under/Good |
| 60-69% | X-Y | ~65% | Over/Under/Good |
| 70-79% | X-Y | ~75% | Over/Under/Good |
| 80-89% | X-Y | ~85% | Over/Under/Good |
| 90-100% | X-Y | ~95% | Over/Under/Good |

### Agent Accuracy
| Agent | Record | Accuracy |
|-------|--------|----------|
| Statistical | X-Y | Z% |
| Matchup | X-Y | Z% |
| Recency | X-Y | Z% |
| Historical | X-Y | Z% |

### Key Patterns
- [Pattern 1: e.g., "Engine underweighted steal rate vs TO rate mismatches"]
- [Pattern 2: e.g., "Low-confidence unanimous picks (sub-65%) went 2-3 — consensus masked uncertainty"]
```

## Rules

- Never editorialize beyond what the data shows
- "Lesson" entries must be actionable — something that could change a future pick, not just "we were wrong"
- Track agent-level accuracy to surface which analyst lens is most/least reliable
- Confidence calibration is the most important output — are 70% picks actually winning 70% of the time?
