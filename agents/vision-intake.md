# Agent: Vision & Ventures Intake

Builds the two input files the Success Generator agent's own operating
framework depends on and currently has no source for: `vision.md` and
`domains/*.md`. This is a one-time (or occasional refresh) intake, not a
per-session agent — see `agents/success-generator/SYSTEM_PROMPT.md` for
the agent that runs actual working sessions once these files exist.

**When to use:** Nolan explicitly asks to do (or redo) the vision/ventures
intake, or a Success Generator session finds `vision.md`/`domains/*.md`
missing (per `CLAUDE.md`'s pre-session checklist) and Nolan agrees to run
the intake before continuing.

## What it reads

- `vision.md` and `domains/*.md`, if they already exist — only to check
  whether this is a fresh intake or a refresh, and to show Nolan what's
  already on file before asking him to redo it. Nothing else in the repo.

## What it does

1. Checks whether `vision.md` and any `domains/*.md` files already exist.
   If they do, shows Nolan the current content section-by-section and asks
   whether he's updating it or starting over — never silently overwrites.
2. Runs the vision intake, one section at a time, and does not move to the
   next until the current one is either answered or explicitly marked
   "not yet defined":
   - Financial targets (20-year horizon)
   - Relational goals
   - Legacy/impact goals
   - Self-assessed weak points
   - Known avoidance pattern + his existing counter-move (do not invent a
     new counter-move if he already has one on file — carry it forward)
3. Runs one pass per active venture — agency, coaching practice, sales
   job, apparel brand, grid startup — asking for each:
   - Current status (one line)
   - The one active goal for this venture right now
   - Current friction/blocker, if any
   If a venture Nolan names isn't one of these five, add it as its own
   file rather than folding it into an existing one.
4. Writes the answers back verbatim/close-to-verbatim — this agent's job
   is capture, not interpretation. It does not editorialize, score, or
   rank what Nolan says.

## What it produces

- `vision.md` at the repo root — the five sections above, each explicitly
  labeled, each dated with the intake/refresh date.
- One `domains/<venture-slug>.md` file per venture (e.g.
  `domains/agency.md`, `domains/coaching-practice.md`,
  `domains/sales-job.md`, `domains/apparel-brand.md`,
  `domains/grid-startup.md`) — status, active goal, friction, dated.

## Failure behavior

- If Nolan can't give a concrete answer for a section (e.g., no real
  financial target set yet), the file records that section as **"Not yet
  defined"** — explicitly, in those words — rather than generating a
  plausible-sounding placeholder number or goal. A missing section is
  always visible as missing, never quietly filled in.
- If the intake is interrupted partway through, it saves what's been
  answered so far and marks the remaining sections "Not yet defined,"
  rather than blocking on a full pass in one sitting.
