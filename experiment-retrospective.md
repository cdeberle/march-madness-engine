# Experiment Retrospective: Claude's 2026 NCAA Bracket

## The Premise

Fill out a complete 63-game March Madness bracket using Claude Code with web search, four specialist sub-agents, and a formal debate protocol. All 63 picks locked before the Round of 64 tips off — no adjustments, no course corrections, no second chances. Pick once, watch it play out.

The engine analyzed the bracket sequentially — R64 matchups first, then derived R32 from those picks, S16 from those, and so on through the championship — but all of that research happened pre-tournament. The bracket was submitted as a single artifact.

## The Result

**42-21 (66.7%)**

| Round | Record | Accuracy |
|-------|--------|----------|
| Round of 64 | 24-8 | 75.0% |
| Round of 32 | 11-5 | 68.8% |
| Sweet 16 | 5-3 | 62.5% |
| Elite 8 | 2-2 | 50.0% |
| Final Four | 0-2 | 0.0% |
| Championship | 0-1 | 0.0% |

For context: the average ESPN Tournament Challenge bracket scores ~42-45 correct picks out of 63 in a typical year. The engine landed at the low end of that range. Not embarrassing, not impressive. The early rounds carried the record; the late rounds cratered it.

---

## What the System Got Right

### 1. The four-agent architecture produced genuine analytical depth

Each agent brought a lens the others didn't have. The Matchup Analyst identified specific scheme collisions (Arizona's paint offense vs Purdue's 342nd rim defense, Michigan's interior D vs Arizona's low 3PT volume) that pure efficiency comparisons missed. The Recency Analyst surfaced roster absences (Wilson OUT for UNC, Quaintance/Knox/Lowe OUT for Kentucky) that invalidated season-long stat lines. The debate layer forced these perspectives to compete rather than blend into mush.

The best example: the pre-tournament bias correction. After the initial bracket produced an all-chalk Sweet 16, we audited the tiebreaker mechanics before locking picks and found the Statistical Analyst was systematically resolving every split toward the higher seed. Two R64 picks were flipped (UNC → VCU, Kentucky → Santa Clara) and both were analytically sound — VCU won, and Santa Clara led with 2.4 seconds left before a half-court miracle. The system was capable of self-correction when we examined it structurally.

### 2. High-confidence picks were money

Games where the engine had 70%+ confidence: **15-1 in R64, continued strong through R32**. When the system was genuinely sure, it was right. The calibration problem was exclusively in the 55-68% range — the "soft lean" zone where the engine treated mild favorites as moderate ones.

### 3. The context-reset-per-round research methodology was correct

Each round's analysis ran in a fresh conversation to prevent narrative contamination from earlier rounds' research. This meant the engine never talked itself into a late-round pick because it had "already invested" in a team's path during earlier analysis. The R64 analysis didn't bleed into the R32 analysis, which didn't bleed into the S16, and so on. Each projected matchup was evaluated independently on its own terms.

### 4. The structured output (picks.json, analysis.md, results.json, retrospective.md) made the experiment trackable

Every pick had a paper trail: which agents agreed, what data they cited, what the confidence meant. When results came in, we could trace exactly why each miss happened — was it bad data, bad weighting, a structural gap, or irreducible randomness? Most bracket exercises don't have this kind of auditability.

---

## What the System Got Wrong — Structurally

These aren't "we should have picked Michigan over Arizona." These are design flaws that would persist across any tournament, any year.

### 1. The engine didn't evaluate path robustness before locking the bracket

Every bracket lives and dies by cascading picks. Picking Florida in R32 implicitly means picking Florida in the S16 and beyond. The engine built the bracket sequentially (R64 picks → derive R32 matchups → analyze those → derive S16, etc.), which meant each later-round analysis assumed the prior round's picks were correct. That's fine as a research methodology, but the engine never stepped back and asked: "How confident am I in the entire path, not just this one game?"

The South region is the case study. The engine picked Florida over Iowa in R32 at 83% confidence. That single pick anchored the entire South path — Florida over Vanderbilt in S16, Houston over Florida in E8, Duke over Houston in F4. Iowa won 73-72, and every downstream pick was dead. Five consecutive misses from one region, all rooted in one game.

Before locking, the engine should have evaluated which paths were "fragile" (dependent on a coin-flip game) versus "robust" (the projected winner advances regardless of opponent). A Final Four pick that runs through a 57% R32 game is really ~57% × downstream probability to even be relevant. That math should have informed where to take safer paths to protect high-value late-round picks.

### 2. The debate protocol's tiebreaker hierarchy was wrong

Three tiebreaker-resolved games in the late rounds. The protocol used this hierarchy:
1. Statistical Analyst breaks the tie (if confidence ≥ 56%)
2. If voided, go to agent count (3+ on one side wins)
3. If still 2-2, situational factors break it

The problem: **"situational factors" defaulted to roster availability over schematic fit.** In the Final Four, Arizona vs Michigan was a 2-2 split. The tiebreaker went to Arizona because Michigan was missing two rotation players. Michigan won by 18. The Matchup Analyst had called the exact mechanism — Mara's rim protection neutralizing Arizona's paint-dependent, low-3PT-volume offense — at 57% confidence. It was the most specific, falsifiable thesis in the debate, and the protocol ranked "team X is missing players" above it.

**The fix:** Schematic structural counters (where Team A's primary offensive identity is directly neutralized by Team B's defensive scheme) should outrank roster depth gaps in tiebreakers. A team can overcome a thin bench; it can't overcome having its entire playbook invalidated.

### 3. The agents had overlapping blind spots instead of complementary ones

All four agents researched the same sources (ESPN, Sports Reference, CBS Sports) and frequently converged on the same narrative. When they all agreed at 61-66% confidence, it felt like consensus but was actually four versions of the same read. The "unanimous" label masked the fact that the agents weren't truly independent.

The symptom: **6 of 8 R64 misses were unanimous picks.** If the agents were genuinely independent, a 4-0 miss should be rare. It wasn't — because they shared sources, anchored on the same efficiency metrics, and had no agent whose job was to stress-test the consensus pick.

### 4. No agent was responsible for "why does the favorite lose?"

The current agents each evaluate from their own lens and output a pick. Nobody's job is to ask: "OK, the consensus says Duke — now, specifically how does Duke lose this game?" A dedicated adversarial agent would have forced the system to articulate the loss scenario and evaluate its probability, rather than treating risk factors as footnotes.

This matters most in the 55-68% zone where most misses occurred. The engine would note "risk: UConn's Hurley is 15-5 in the tournament with 2 titles" as a bullet point under Duke's pick — then give Duke 64%. An adversarial agent would have been forced to build the full UConn case and assign it a probability, making the true uncertainty harder to ignore.

### 5. Conference-physicality and talent-floor gaps were systematically underweighted

Three R64 misses and two later misses shared a pattern: the engine picked a mid-major or struggling power-conference team over a "slumping" but deeper/more physical opponent. Texas A&M's 18 forced turnovers against Saint Mary's. Texas Tech's 91-71 blowout of Akron. Tennessee's 43-22 rebounding against Iowa State. Michigan's 91-73 demolition of Arizona.

The agents evaluated efficiency metrics, which don't capture "this team's worst players are still more athletic than your best players." No agent was tasked with evaluating raw talent depth or physical mismatch — the things that don't show up in adjusted efficiency but determine who dictates the style of play when the game gets physical in March.

---

## Agents That Were Missing

### 1. Adversarial / Devil's Advocate Agent

**Role:** Takes the consensus pick and builds the strongest possible case against it. Outputs a "loss probability" and a specific loss scenario. Forces the orchestrator to contend with the downside rather than footnoting it.

**Why it matters:** The engine's worst calibration was in the 60-69% bucket — games where it leaned one way but shouldn't have been confident. An adversarial agent would compress overconfident picks back toward 50-55% by making the counter-case visceral rather than abstract.

### 2. Market / Consensus Agent

**Role:** Pulls betting lines, ESPN Tournament Challenge pick percentages, CBS/SI bracket expert picks, and model consensus (e.g., FiveThirtyEight-style aggregators). Reports where the engine's pick diverges from market consensus and by how much.

**Why it matters:** The market is a powerful aggregator of information the engine can't access (injury intel, practice reports, locker room dynamics, coaching adjustments). When the engine's pick diverges significantly from the market, that's either an edge or a red flag — but without this agent, the engine had no way to know. The South region (where the engine projected Florida and Houston going deep, while experts leaned Houston on home court and Illinois as a dark horse) is exactly where market signal would have added value.

This isn't about deferring to Vegas. It's about having a systematic way to detect when the engine's read is an outlier — and forcing the orchestrator to explain why it's smarter than the crowd.

### 3. Physicality / Talent-Floor Agent

**Role:** Evaluates raw roster talent (NBA draft stock, recruiting rankings, transfer portal acquisitions), physical matchups (size, athleticism, depth), and conference-adjusted physicality. Specifically answers: "When this game gets ugly and half-court execution breaks down, which team has the athletes to win a rock fight?"

**Why it matters:** The engine's efficiency-first worldview assumed games would be played at the level the stats described. But tournament games compress toward physicality, especially in later rounds. Three of the engine's clearest miss patterns — mid-major efficiency over power-conference depth, perimeter teams getting out-rebounded by 20, and "slumping" teams with NFL-caliber athletes overwhelming smaller opponents — all trace to this blind spot.

### 4. Simulation / Variance Agent

**Role:** Instead of outputting a single pick, runs a simple Monte Carlo-style analysis: "If these two teams played 100 times, what's the distribution of outcomes?" Factors in shooting variance (a 35% 3PT team will have games at 25% and 45%), turnover variance, and free throw variance. Outputs a win probability and the width of the confidence interval.

**Why it matters:** The engine treated every game as deterministic — Team A's eFG% vs Team B's defensive eFG%, therefore Team A wins. But single-elimination basketball is governed by variance. A team that shoots 35% from three will have a game where they go 2-of-15 and a game where they go 9-of-15. The engine had no mechanism to model this, which is why it was overconfident on games where the favorite's edge was narrow and shooting-dependent.

This agent would also naturally solve the "soft lean overconfidence" problem: a game where the simulation says 54-46 should never be labeled 65% confidence regardless of what the other agents think.

---

## Research Structure Changes

### 1. Source diversification per agent

All four agents pulled from ESPN BPI, Sports Reference, and CBS Sports. They should have had **non-overlapping primary sources** to reduce correlation:
- Statistical → ESPN BPI + EvanMiya (keep as-is)
- Matchup → Scouting reports, coaching interviews, press conferences, game film breakdowns (CBS/Yahoo/The Athletic previews)
- Recency → Beat reporters, social media injury intel, practice reports, pressers
- Historical → Sports Reference archives exclusively

This would make their assessments genuinely independent rather than four interpretations of the same ESPN page.

### 2. Explicit confidence anchoring rules

The agents frequently converged on suspiciously similar confidence numbers (Kentucky: 64/64/64/64). The schema should enforce: **no two agents may output the same confidence percentage.** This is a crude but effective de-anchoring mechanism. If your number matches another agent's, you're probably anchoring on a shared prior rather than deriving from your own data.

### 3. Structured "what would change my mind" output

Each agent should be required to output not just risk factors, but a **specific trigger**: "If [X happens], my pick flips." For instance: "If Ngongba is confirmed OUT, my confidence drops from 67% to 52% and my pick flips to UConn." This gives the orchestrator a decision tree rather than a flat assessment, and makes uncertainty actionable rather than decorative.

---

## What No System Can Fix

A few things worth naming honestly:

**Miracle shots are real.** Two of the engine's cleanest misses — Kentucky's half-court buzzer-beater against Santa Clara and Mullins' 35-foot three with 0.4 seconds against Duke — were unmodelable. The engine had the right team winning with 2.4 seconds left in one game and leading by 19 at halftime in the other. These aren't analytical failures. They're the reason the tournament exists.

**Single-elimination is not a meritocracy.** The best team doesn't always win a one-game sample. Michigan shot 13.3% from three in the championship and won because they went 25-of-28 from the free throw line. On a different night, those free throws rim out and UConn wins. The engine can identify the better team; it can't guarantee the better team wins on that particular Tuesday.

The goal isn't 63-0. It's a system that's well-calibrated (70% picks win ~70% of the time), transparent about uncertainty, and improvable across years. On calibration, the engine was solid in the high-confidence range and overconfident in the middle. That's a fixable problem.

---

## Summary: If We Run This Again

| Change | Category | Impact |
|--------|----------|--------|
| Add Adversarial Agent | New agent | Compresses overconfident picks in the 60-68% zone |
| Add Market/Consensus Agent | New agent | Detects when engine is an outlier vs crowd wisdom |
| Add Physicality/Talent Agent | New agent | Closes the power-conference depth blind spot |
| Add Simulation/Variance Agent | New agent | Replaces deterministic picks with probabilistic ranges |
| Revise tiebreaker: schematic fit > roster gaps | Protocol | Prevents overruling the best analytical case on depth alone |
| Diversify sources per agent | Research | Makes agent independence real, not cosmetic |
| Require "what flips my pick" trigger | Schema | Makes uncertainty actionable |
| Evaluate path robustness before locking | Protocol | Protects high-value late-round picks by stress-testing upstream dependencies |
| Enforce unique confidence scores | Schema | Prevents anchoring between agents |
| Historical base-rate ceiling on confidence | Protocol | A 5v12 never exceeds 68%, a 1v2 never exceeds 62%, etc. |

**Predicted champion: Duke. Actual champion: Michigan.**
**The engine picked Michigan correctly in every round Michigan played — then picked against them once, in the Final Four, and it cost the entire bracket.**

That's March.
