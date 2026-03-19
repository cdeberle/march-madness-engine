# Engineering Changelog — Session 1 (2026-03-18)

## Agent Configuration

### Sub-Agent Model Selection
- **Decision:** All sub-agents use `model: "sonnet"`
- **Why:** Token cost control. Opus would produce marginally better analysis but at 5-10x the token cost per agent. Sonnet's research + JSON output quality was sufficient for this use case.
- **Added to:** CLAUDE.md, orchestrator.md

### Concurrency Cap: 4 Agents Max
- **Decision:** Process one matchup at a time (4 analysts in parallel), then move to the next
- **Why:** User wanted visibility into agent actions in real time. The original orchestrator allowed up to 8 matchups at a time (32 concurrent agents), which was unmonitorable and token-expensive.
- **Added to:** CLAUDE.md, orchestrator.md

### Foreground-Only Execution
- **Decision:** Never use `run_in_background: true`
- **Why:** Background agents complete silently — user can't monitor their actions or intervene. Foreground keeps everything visible.
- **Added to:** CLAUDE.md

## Prompt Engineering

### Search Cap (MAX 5-8)
- **Decision:** Every agent prompt includes "MAX 5-8 web searches" instruction
- **Why:** Without this, agents were making 30-60 web searches per dispatch. Game 3's statistical agent made 61 tool calls and took 5 minutes. After adding the cap, agents dropped to 5-10 searches and completed in ~1 minute.
- **Impact:** Per-game session cost dropped from ~5% to ~3% of context window. This single change extended session capacity from ~10 games to ~13-15 games.
- **Added to:** CLAUDE.md (as a sub-agent rule), individual agent dispatch prompts

### Prompt Compression
- **Decision:** Shortened agent prompts progressively across the session
- **Before (Games 1-3):** Full role description, complete methodology, full schema with field rules (~400 words per prompt)
- **After (Games 5+):** Role + search cap + blocked sources + matchup + JSON template (~150 words per prompt)
- **Why:** Verbose prompts consumed unnecessary input tokens without improving output quality. Agents performed identically with compact prompts.

## Data Sources

### Source Accessibility Audit
- **Decision:** Tested all referenced sources via WebFetch before the analysis run
- **Findings:** 4 of 9 sources were inaccessible (paywall, bot-blocked, or down)
- **Action:** Replaced blocked sources and added explicit "Blocked sources — do NOT use" warnings to each agent file with fallback instructions

| Blocked | Reason | Replacement |
|---------|--------|-------------|
| KenPom.com | Paywall (403) | ESPN BPI + EvanMiya |
| Barttorvik.com | Cloudflare bot-block | EvanMiya + Sports Reference |
| The Athletic | Paywall | CBS Sports + Yahoo Sports |
| Warren Nolan | 403 | Sports Reference archives |

### EvanMiya Fallback Clause
- **Decision:** Added "If EvanMiya data is behind a login wall, fall back to ESPN BPI and Sports Reference" to Statistical and Matchup analyst files
- **Why:** EvanMiya showed signs of a freemium model during testing. Couldn't confirm all data was free. Agents need a documented fallback so they don't stall.

## Session Management

### Checkpointing Protocol
- **Decision:** Write results to disk after every single game (picks.json, analysis.md, checkpoint.json)
- **Why:** Token exhaustion mid-run would lose all unsaved work. With 32 games requiring multiple sessions, incremental saves are critical.
- **Added to:** CLAUDE.md

### Handoff System
- **Decision:** Create HANDOFF.md when approaching ~15% remaining session context
- **Contents:** Progress state, upsets picked, close calls, key learnings, remaining matchups, session budget estimate
- **Why:** checkpoint.json tracks mechanical state (which game is next). HANDOFF.md captures institutional knowledge — what went wrong, what worked, edge cases encountered — so the next session doesn't repeat mistakes.
- **Added to:** CLAUDE.md

### Session Budget Documentation
- **Decision:** Document actual token cost per game in CLAUDE.md
- **Initial estimate:** ~5% per game (10-15 games/session)
- **Actual (post search-cap):** ~3% per game (13-15 games/session)
- **Why:** Future sessions need planning info immediately, not trial-and-error discovery.

## Debate Protocol Clarifications

### Recency Override Scope
- **Observation:** Game 13 (UNC vs VCU) — Wilson OUT (19.8 PPG), recency agent flipped to VCU, but both data-tier agents still picked UNC. Override was NOT applied.
- **Clarification established:** Recency override only triggers when the roster change is severe enough that data agents split or flip. If BPI/data agents already price in the injury and still favor the original team, the override doesn't apply.
- **Not yet codified** in orchestrator.md — consider adding in a future session.
