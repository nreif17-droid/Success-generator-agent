# Agent: Session Carry-Forward

Distills the raw session logs in `agents/success-generator/sessions/` into
a single current-state summary, so a new Success Generator session starts
from what's actually still open rather than re-reading every past log in
full (or worse, nothing at all).

**When to use:** Nolan asks for the summary to be refreshed, or a new
dated file lands in `agents/success-generator/sessions/` and Nolan agrees
to refresh the summary before starting the next working session.

## What it reads

- Every dated `YYYY-MM-DD-session.md` file in
  `agents/success-generator/sessions/`. Excludes `sessions/README.md` (the
  template) and its own output file (`sessions/CURRENT-STATE.md`) — never
  reads its own prior summary as if it were a session log.
- Nothing else. Not `vision.md`, not `domains/*.md` — this agent's job is
  to distill session history specifically, not restate current venture
  status (that's what `domains/*.md` is for).

## What it does

1. Counts how many session logs exist. Reports this count plainly at the
   top of its output — so anyone reading it immediately knows how much
   history the summary is actually built from.
2. For each session log, pulls its **"Follow-up / next session check-in"**
   items verbatim, and checks whether a later session addressed them (a
   later log's content actually speaks to the same item). Sorts into:
   - **Still open** — no later session addressed it.
   - **Resolved** — a later session shows it was addressed, with which
     session resolved it.
3. Looks across all sessions (only meaningful with 2+) for **recurring
   patterns** — the same avoidance-pattern trigger, the same blocker, or
   the same venture friction showing up in more than one session log —
   and names each recurring item with which sessions it appeared in.
4. Does not touch `domains/*.md` or `vision.md`. If a session's content
   implies a venture file is now stale (e.g. a status change mentioned in
   a session that doesn't appear in the matching `domains/*.md`), it flags
   this as a note for Nolan to reconcile — it does not edit those files
   itself.

## What it produces

- `agents/success-generator/sessions/CURRENT-STATE.md` — **overwritten**
  each run (this is a live current-state snapshot, not an accumulating
  log): session count, still-open follow-ups (with source session dated),
  resolved follow-ups (with which session resolved them), and recurring
  patterns found (or explicitly "none identified yet").

## Failure behavior

- With **zero** session logs, it says exactly that — "No session logs
  exist yet; nothing to summarize" — and does not produce a
  `CURRENT-STATE.md` at all.
- With **exactly one** session log, it can still list that session's open
  follow-ups (nothing to resolve/cross-reference yet), but explicitly
  states **"Not enough session history yet to identify recurring
  patterns (need 2+ sessions)"** rather than presenting a single
  occurrence as a pattern.
- If a "follow-up" item is ambiguous about whether a later session
  actually resolved it (partial overlap, not a clean match), it's left in
  **Still open** rather than guessed as resolved — false "resolved" status
  is worse than an item staying visible one session longer than necessary.
