# Optimize

Efficient study workspace management guide.

When a user says to follow this document, new additions must satisfy the
requirements below, not merely copy the text style. Use the concise wording and
Markdown structure here as a style model, but treat the principles, architecture,
runtime strategy, and budgets as content constraints for the new addition.

Study-specific rules still belong in their owner documents, not here. Add the
smallest canonical rule that meets these requirements and avoids future token
waste.

## Core Principles

- Net-negative: Add only if you delete/merge more.
- Continuity First: Protect durable study context.
- Indexes: Use `bootstrap.md` and `loadout.md`. Skip full-tree scans.
- Readable Format: Standard Markdown, clear headers, concise phrasing.
- Truth Source: Markdown > derived indexes.
- Human-Friendly: Simple names, clear labels, in-file metadata.
- No Duplication: Point to canonical files.
- Prune Aggressively: Delete, merge, or compress text whenever the remaining
  canonical rule/evidence stays accurate and usable.
- Ignore Junk: Exclude caches, generated files, logs, and private local state.

## Workspace Architecture

- Canonical Homes:
    - `bootstrap.md`: `loadout.md` pointer.
    - `loadout.md`: Route map and summary.
    - `memory/current.md`: Durable study facts.
    - Root method files: Topic-specific methods.
- Boundaries: Public/private separation.
- Domain Separation: `study` indexes only study methods and study facts.

## Runtime Strategy

- Narrow Load: Load only the relevant study method.
- Search First: Use `rg` before reading long files.
- Snippet Only: Target relevant sections.
- Summarize: Preserve conclusions, not raw dumps.
- Phased Context: Load what the current step needs.
- Working State: For long study/research tasks, keep a compact live state:
  question, method, sources used, conclusions, uncertainty, and next check.
- Semantic Dedup: If a fact is already captured in a method file, source map, or
  memory summary, reference it instead of repeating the full text.
- Parallelize: Handle tasks during wait times.
- Escalation: Don't improvise; install or ask for permission.

## Soft Budgets

- Default Load: `bootstrap.md` + `loadout.md`.
- Paper Reading: Abstract, figures/tables, conclusion, then needed sections.
- Problem Solving: Transcribe, solve, check.
- Research Questions: Define question, evidence needed, targeted retrieval,
  synthesis, caveat/check.
- Multi-Agent: Compact objective/scope/evidence packets.

## Context Profiles

- Shared: Use `token-system.md` for always-on context discipline and long-task
  resume packets.
- Paper Reading: Keep source maps, selected anchors, claim/evidence/limitation
  notes, and terminology uncertainty. Do not carry full paper text unless making
  an annotation artifact.
- Problem Solving: Convert images to compact problem text, solve once, and keep
  the final method plus check instead of raw scratch work.
- Answer Quality: Keep the task inference, evidence boundary, and repair lesson
  only when reusable; discard failed phrasings and transient debate.
