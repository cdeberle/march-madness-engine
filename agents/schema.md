# Agent Output Schema

Every specialist agent MUST return its assessment in this exact JSON format. The orchestrator parses this to run the debate/consensus layer.

```json
{
  "matchup": {
    "team_a": { "name": "Team Name", "seed": 1 },
    "team_b": { "name": "Team Name", "seed": 16 }
  },
  "pick": "Team Name",
  "confidence_pct": 78,
  "key_factors": [
    "Specific data-backed factor (cite the number)"
  ],
  "risk_factors": [
    "What could go wrong for the picked team"
  ],
  "sources": [
    "Source name (accessed YYYY-MM-DD)"
  ],
  "data_gaps": [
    "Any metrics you could not find reliable data for"
  ],
  "upset_flag": false
}
```

## Field Rules

- **pick**: Must be one of the two team names in the matchup. No hedging.
- **confidence_pct**: Integer 50-100. If you'd pick below 50, flip your pick.
  - **90-100%**: Extreme mismatch — would be historic upset if picked team loses
  - **75-89%**: Clear favorite — opponent has identifiable paths to win
  - **60-74%**: Lean — meaningful uncertainty exists
  - **50-59%**: Near toss-up — slight edge call
- **key_factors**: 2-4 factors. Every factor must include a specific stat, date, or verifiable claim. No vague statements like "they're a good team."
- **risk_factors**: 1-3 risks. What would need to happen for your pick to lose?
- **sources**: Cite where you found your data. Include access date. If you couldn't verify a stat, put it in data_gaps instead.
- **data_gaps**: Be honest. If KenPom data wasn't available, say so. If injury status is unclear, say so. This field directly affects your weight in the debate layer.
- **upset_flag**: true if your pick is the lower seed.

---

## Orchestrator Output Schema

The orchestrator writes `picks.json` per round in this format:

```json
{
  "round": "round-of-64",
  "date_generated": "YYYY-MM-DD",
  "region": "East",
  "matchups": [
    {
      "game_number": 1,
      "team_a": { "name": "Team Name", "seed": 1 },
      "team_b": { "name": "Team Name", "seed": 16 },
      "winner": "Team Name",
      "confidence_pct": 89,
      "consensus_type": "unanimous|majority|split|recency_override",
      "upset": false,
      "deciding_factor": "Brief explanation",
      "agent_picks": {
        "statistical": { "pick": "Team Name", "confidence_pct": 92 },
        "matchup": { "pick": "Team Name", "confidence_pct": 85 },
        "recency": { "pick": "Team Name", "confidence_pct": 88 },
        "historical": { "pick": "Team Name", "confidence_pct": 90 }
      }
    }
  ]
}
```

Agent keys in `agent_picks`: `statistical`, `matchup`, `recency`, `historical`.
