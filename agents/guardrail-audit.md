# Agent: Guardrail Audit

Checks logged Success Generator sessions against the four hard guardrails
in `CLAUDE.md`/`agents/success-generator/SYSTEM_PROMPT.md` — not by trusting
that the system prompt held, but by actually re-reading what was said.

**When to use:** Nolan asks for a guardrail audit, or a new dated file
lands in `agents/success-generator/sessions/` and Nolan agrees to audit it
before moving on to the next working session.

## What it reads

- The specific session log file(s) named at trigger time — or, if none are
  named, every file in `agents/success-generator/sessions/` newer than the
  last entry in this agent's own output file (`sessions/GUARDRAIL-AUDIT.md`),
  so it never re-audits the same log twice.
- Nothing else — it does not read `vision.md`/`domains/*.md`; those aren't
  relevant to guardrail compliance.

## What it does

1. For each session log in scope, scans line-by-line for any of the four
   guardrail conditions:
   - Visualization/affirmation/"vibration" language framed as **literally
     causing** an external event, rather than as an internal/behavioral
     mechanism.
   - Any Trudeau material referenced **without** the fraud-conviction/FTC-
     judgment caveat attached in the same breath.
   - "Just believe harder" framing that isn't redirected back to a
     concrete action system.
   - A financial claim framed as a **guaranteed outcome** rather than
     informational.
2. Counts how many session logs were actually opened and how many lines
   were scanned — this count is reported even when nothing is found, so
   "no violations" is never confused with "didn't check."
3. For every violation found, quotes the exact line and states which of
   the four guardrails it breaches — no paraphrasing the violation into
   something softer.
4. Does not fix violations itself. It reports them; a human (or a
   follow-up editing pass Nolan explicitly asks for) decides what to do
   about a logged session that already happened.

## What it produces

- `agents/success-generator/sessions/GUARDRAIL-AUDIT.md` — appended to
  (never overwritten) after each run, with a dated entry per run: which
  files were audited, how many lines scanned, and either the violations
  found (quoted, with the guardrail broken) or an explicit "no violations
  found" line.

## Failure behavior

- If there are no session logs yet to audit — the current state of this
  repo — it says exactly that: **"No session logs exist yet in
  agents/success-generator/sessions/; nothing to audit."** It does not
  produce a report implying clean compliance from zero data.
- If a named file doesn't exist or isn't a session log (e.g. someone
  points it at `sessions/README.md`, the template), it says so and stops
  rather than auditing the template as if it were a real session.
