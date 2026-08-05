# Skill Recommendations — Success Generator Agent repo

Scouted: 2026-08-05
Scope: `nreif17-droid/success-generator-agent`

## 1. What's actually in the repo right now

- **Git history:** one commit (root commit, same-day). No prior usage, no
  prior agents, no prior skills. This matters for the ranking below — most
  of what follows is a **structural gap** (something the spec references
  but the repo has no file for), not **observed friction** (a problem that
  showed up after real use), because there hasn't been real use yet.
- **No `CLAUDE.md`** anywhere in the repo.
- **No `/domains` or equivalent status files.** The spec and `README.md`
  both explicitly list "current active ventures (agency, coaching practice,
  sales job, apparel brand, grid startup)" and "Nolan's stated 20-year
  vision (financial targets, relational goals, legacy/impact goals,
  self-assessed weak points, known avoidance pattern)" as inputs the agent
  draws on — but no file in the repo captures any of it. It exists only as
  a sentence in the README, not as data.
- **`agents/success-generator/`** — `SYSTEM_PROMPT.md` (the loaded prompt)
  and `knowledge/` (7 files, one per author/claim-source, all populated).
  This part of the repo is complete relative to spec.
- **`agents/success-generator/sessions/`** — contains only `README.md`
  (the template + instructions). **Zero dated session files exist.** No
  session with Nolan has been logged yet.
- **No other `/agents/*.md` files** — i.e. no scout/skill-builder/other
  utility agents live in this repo yet (this scouting pass is the first).

## 2. Relevant current best practices (external research)

- **CLAUDE.md as always-loaded context.** The most widely adopted pattern
  in Claude Code (and equivalents — Codex's `AGENTS.md`, Cursor's
  `.cursorrules`) is a short, opinionated root file injected into context
  at the start of every session: real paths, the gotchas that burn a
  session, explicit "do this, not that" rules, kept under ~200 lines.
  Global/always-true rules belong in `CLAUDE.md`; domain-specific,
  occasionally-needed workflows belong in skills that load on trigger, not
  in the always-on file. *(sources: [ayautomate.com — best CLAUDE.md
  examples](https://www.ayautomate.com/blog/best-claude-md-examples),
  [mcp.directory — Claude Code best
  practices](https://mcp.directory/blog/claude-code-best-practices))*
- **Markdown-file memory for durable, cross-session facts.** The pattern
  that's converged on across agent frameworks (Spring AI's AutoMemoryTools,
  OpenAI's context-personalization cookbook, general agent-memory surveys)
  is: keep a *curated* markdown memory — a small set of facts worth keeping
  forever (user goals, standing decisions, corrections) — separate from raw
  session transcripts, and inject a summary of it at the start of each new
  session. Raw logs alone (what this repo currently has as its only
  planned artifact) are explicitly called out as insufficient on their own
  — the win comes from something that *distills* them.
  *(sources: [dev.to — AI agent memory management,
  markdown](https://dev.to/imaginex/ai-agent-memory-management-when-markdown-files-are-all-you-need-5ekk),
  [Spring AI — AutoMemoryTools](https://spring.io/blog/2026/04/07/spring-ai-agentic-patterns-6-memory-tools/))*
- **Identity-based habit/accountability systems** in 2025–2026 lean on: a
  "minimum protects identity, stretch builds capacity" two-tier target
  (so a missed day doesn't break the system), low-pressure/guilt-free
  tracking, and *some* accountability structure with real visibility
  (peer or logged). This is directly relevant to the spec's "mastermind
  principle" and "what gets tracked, what gets reviewed" system-building
  step. *(source: [habitbox.app — identity-based habits
  guide](https://habitbox.app/blog/identity-based-habits))*

## 3. Cross-referenced recommendations

### Recommendation A — `CLAUDE.md` for this repo
- **Gap it addresses:** Claude Code has no always-loaded orientation file.
  Every session currently starts cold with no instruction to read the
  vision/domains inputs (once they exist), no instruction to check
  `sessions/` for the most recent log before starting a new one, and no
  statement of the guardrails as enforceable rules rather than prose in a
  README.
- **Evidence for the gap:** confirmed directly — `find` over the repo
  shows no `CLAUDE.md` at any level.
- **Rough sketch:** short root `CLAUDE.md` (~40–80 lines): what this repo
  is, where the system prompt lives, "before a session: read the most
  recent 1–2 files in `sessions/`, plus `vision.md`/`domains/*.md` once
  they exist," and the four guardrails restated as hard rules.
- **Data/need exists now?** **Yes.** Needs nothing beyond what's already
  in the repo. This is pure repo hygiene against a well-established,
  solved pattern.
- **Rank: build now.**

### Recommendation B — Vision & ventures intake (`vision.md` + `domains/*.md`)
- **Gap it addresses:** the agent's own spec says it draws on "Nolan's
  stated 20-year vision" and "current active ventures" as primary inputs,
  but there is no file holding either. Right now the agent has nothing to
  actually read for the inputs its own operating framework depends on.
- **Evidence for the gap:** direct — `README.md` §"Inputs it draws on"
  names five ventures and a five-part vision structure; `grep` for any of
  those terms outside the README returns nothing.
- **Rough sketch:** a short intake-style agent/skill that runs a structured
  conversation to produce `vision.md` (financial/relational/legacy targets,
  self-assessed weak points, the named avoidance pattern) and one file per
  venture under `domains/` (agency, coaching practice, sales job, apparel
  brand, grid startup) — status, current friction, one active goal each.
- **Data/need exists now?** **Yes** — this is Nolan's existing, already-
  decided information; it just hasn't been captured as a file. No new
  usage history is required to build the *intake* skill, only to run it
  once against him.
- **Rank: build now** (second, after CLAUDE.md — the sessions flow in
  Recommendation A's `CLAUDE.md` references these files, so having them
  exist first avoids a dangling reference).

### Recommendation C — Session carry-forward / memory summary
- **Gap it addresses:** the sessions template captures one session in
  isolation; nothing distills prior sessions into what the agent should
  remember going in to the next one (open commitments, recurring blocks,
  what was tried and didn't stick). This is exactly the "curated memory
  vs. raw logs" distinction the research surfaced.
- **Evidence for the gap:** structural only — `sessions/` has zero logged
  sessions to summarize. There is no friction yet because there is no
  history yet.
- **Rough sketch (for later):** a skill that reads all `sessions/*.md`
  files, extracts open follow-ups and recurring blocks, and maintains a
  single `sessions/CURRENT-STATE.md` summary file, refreshed after each
  new session is logged.
- **Data/need exists now?** **No.** There is nothing to summarize yet —
  building this before any real sessions exist means designing against
  zero examples of what actually needs carrying forward.
- **Rank: later — revisit once 2–3 real session logs exist.**

### Recommendation D — Habit/accountability tracking integration
- **Gap it addresses:** the spec calls for "concrete weekly/daily
  practices... what gets tracked, what gets reviewed, what the
  mastermind/accountability structure is," but nothing in the repo defines
  *how* tracking actually happens (a file, an external tool, a check-in
  cadence). Best-practice research suggests a two-tier minimum/stretch
  target structure plus a visible accountability point.
- **Evidence for the gap:** structural — referenced in the operating
  framework, no mechanism exists.
- **Rough sketch (for later):** once a real system has been proposed and
  run in a couple of sessions (Recommendation C's prerequisite), a
  lightweight tracker skill/file that logs the specific minimum/stretch
  habits chosen and a weekly-review checklist.
- **Data/need exists now?** **No.** This is downstream of an actual
  session having proposed real habits to track — building it now means
  guessing the shape of a system that hasn't been designed yet.
- **Rank: later — blocked on Recommendation C and at least one real
  session.**

### Item flagged, not ranked — guardrail verification
Nothing in step 2's research surfaced an established, off-the-shelf pattern
for testing that an agent's own guardrails hold over time (e.g., confirming
the Trudeau fraud caveat and the "no literal causation" framing survive
paraphrase/pressure). This looks like a genuinely open problem rather than
a borrowed pattern — worth a dedicated design pass later, not a
recommendation to build today, and not something this report has evidence
is causing friction yet.

## 4. Summary ranking (build-now → later)

| # | Recommendation | Needs new data? | Rank |
|---|---|---|---|
| A | `CLAUDE.md` | No | **Build now** |
| B | Vision & ventures intake | No (Nolan's info exists, just uncaptured) | **Build now, after A** |
| C | Session carry-forward memory | Yes — needs real session logs | Later |
| D | Habit/accountability tracking | Yes — needs a real proposed system from a session | Later, blocked on C |

## Explicitly not done in this report
No skill file has been drafted or committed. Per the scout process, this is
a recommendation report only — next step is for Nolan to approve one
specific recommendation above, then hand off to `agents/skill-builder.md`
with that recommendation as input.
