# March Madness Analysis Engine

NCAA tournament bracket analysis using specialist sub-agents.

## Workflow

When asked to analyze a round, read `agents/orchestrator.md` and follow its process. The orchestrator drives everything — matchup extraction, agent dispatch, debate synthesis, and output generation.

Use the Agent tool to dispatch specialist analysts (`agents/statistical-analyst.md`, `agents/matchup-analyst.md`, `agents/recency-analyst.md`, `agents/historical-analyst.md`). All agents return structured JSON per `agents/schema.md`.

## Sub-Agent Rules

- **Max 4 concurrent sub-agents.** Never launch more than 4 Agent tool calls in a single message. Process one matchup at a time (4 analysts), then move to the next.
- **Foreground only.** Never set `run_in_background: true` — all agents must run in foreground so their actions are visible and monitorable in real time.
- **Model: Sonnet.** Always set `model: "sonnet"` on every Agent tool call to control token usage.
- **Search cap.** Each agent prompt must include `MAX 5-8 web searches` to prevent over-research. Without this cap, agents will make 30-60 searches and consume 3-5x more tokens.

## Session Budget

Each matchup (4 agents + synthesis + logging) consumes ~5% of a session's context window. A single session can process roughly **10-15 games** before needing a handoff.

### Checkpointing

After every game, immediately:
1. Append the result to `output/<round-name>/picks.json`
2. Append the writeup to `output/<round-name>/analysis.md`
3. Update `output/<round-name>/checkpoint.json` (completed games, next matchup, game statuses)

### Handoff

When approaching session limits (~15% remaining), create `output/<round-name>/HANDOFF.md` with:
- Current progress state
- Upsets picked so far
- Key learnings for the next session
- Remaining matchups list

To resume: start a new session and say **"Resume the round-of-64 analysis from the checkpoint."** The new session should read `checkpoint.json` for progress state and `HANDOFF.md` for context and learnings from the prior session.

## Debate Protocol

Data > intangibles. Statistical and Matchup analysts outweigh Recency and Historical.

**Exception:** Factual roster changes (injury, suspension, legal issues) override statistical projections — season-long stats assume a full roster.

## Round Names

`round-of-64`, `round-of-32`, `sweet-16`, `elite-8`, `final-4`, `championship`

## Output

Each round writes to `output/<round-name>/`:
- `picks.json` — structured pick data (deliverable)
- `analysis.md` — detailed writeups (deliverable)
- `checkpoint.json` — progress tracker for multi-session runs (operational)
- `HANDOFF.md` — session transfer context, created when approaching token limits (operational)

## Rules

- Every pick must be statistically justified with cited sources
- No hallucinated stats — flag data gaps honestly
- No narrative-only reasoning (reputation, brand name, "due for a win")
- Full context reset between rounds — each round runs in a new conversation
- Never project beyond the current round
