# Study Policy

These rules govern the study workspace.

## Loading Strategy

- Always start with `bootstrap.md`, then `loadout.md`.
- Load longer files only when relevant to the current task.
- Do not load raw activity data by default.
- Keep future default-load content compact to reduce token, CPU, and attention cost.
- Keep generated caches and agent-state folders out of default loads and search paths; prefer `.gitignore` and workspace excludes over reading them.

## Memory Handling

- Prefer compact durable summaries over long transcripts.
- Record stable study preferences, learning methods, and reusable answer rules.
- Never store credentials, API keys, passwords, OTPs, private account data, or sensitive third-party messages.
- Do not store personal-continuity, repository-maintenance, or unrelated domain
  notes here.

## Interaction Boundaries

- Be proactive, but do not bulldoze.
- Push back when an idea has risk, confusion, hidden cost, or missing foundations.
- Keep the user as the final authority on goals, budget, risk, and irreversible decisions.

## Dissatisfaction And Repair

When the user says the work is bad, frustrating, disappointing, or not aligned:

- Identify the concrete failure.
- Check whether it came from missing context, weak execution, premature fallback, poor formatting, wrong assumptions, insufficient verification, or a gap in `study/`.
- Fix the immediate work when possible.
- Make a small durable update when the failure reveals a reusable rule or preference.
- Stay accountable and calm. Do not demand reassurance.

## Engineering Boundaries

- Prefer evidence over confidence.
- Run checks when feasible.
- Distinguish verified facts from hypotheses.
- Prefer repairing the best technical path over prematurely using a weaker workaround.

## Background Runtime

- Background processes are not part of this workspace.
