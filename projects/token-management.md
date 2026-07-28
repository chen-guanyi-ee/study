# Token And Context Management Method

Load this file when the user asks about token usage, context windows, large
study/research tasks, image-heavy problem solving, paper annotation scope,
multi-agent packets, or reducing unnecessary workspace/tool overhead.

Last updated: 2026-07-28

## Purpose

Token management is answer quality. Spend context on information that changes
the answer, not on repeated discovery, raw transcripts, or full artifacts that
can be reopened by pointer.

Default pattern: orient from compact indexes, retrieve exact evidence, compress
the useful result, then write durable lessons only when they improve future
study work.

## Core Rules

- Index first: start from `bootstrap.md`, `loadout.md`, and the routed
  `projects/*.md` method file.
- Route narrowly: load one study method unless the task is a workspace-wide
  cleanup or cross-method design question.
- Search before read: use `rg`, filenames, headings, source maps, and table of
  contents before opening long files.
- Snippet over whole file: read exact sections, paragraphs, figures, equations,
  or problem statements.
- Summarize observations: convert multiple raw sources into a short working
  synthesis with source pointers.
- Avoid duplicate context: reference existing method files, source maps, and
  memory summaries instead of repeating long rules.
- Separate phases: triage, retrieve, solve/synthesize, verify, and final answer
  each carry only the context needed for that phase.
- Cap tool output: request short outputs, exclude caches/generated logs/private
  state, and avoid full repo packs unless auditing the whole workspace.
- Record compact memory only: durable files capture stable preferences,
  reusable methods, and conclusions, not transcripts or scratch work.

## Three-Layer State

- Loadout: every-turn route map and tiny default context.
- Method file: topic-specific process and quality gates.
- Artifact/source: papers, screenshots, repos, code, notes, and generated output
  loaded only when relevant.

For long tasks, keep a compact working note:

```text
Question:
Method:
Sources used:
Useful facts:
Uncertainty:
Next check:
```

Do not preserve raw source text unless exact quotation, proof, or audit evidence
is required.

## Context Profiles

- Paper Reading: Keep claim -> source location -> evidence type -> limitation.
  Read title, abstract, figures/tables, conclusion, and exact queried sections
  before full-paper annotation. Store terminology uncertainty separately.
- Problem Solving: For images, transcribe the problem first, mark uncertain
  symbols, solve with the shortest valid method, and keep the final check. Do
  not carry raw image discussion after transcription unless visual ambiguity
  remains decisive.
- Research Questions: Define the question, evidence needed, targeted retrieval,
  synthesis, caveat/check, and what evidence would change the answer.
- Answer Quality Repair: Keep only reusable failure lessons: missing context,
  weak verification, wrong assumption, poor format, or premature fallback.
- Cross-Project Study Cleanup: Use shared rules here, but let each method file
  decide its own evidence granularity. Do not force paper, problem-solving, and
  open research notes into one identical template.

## Visual Inputs

- Convert screenshots/images to compact observations: visible text, symbols,
  units, UI state, error markers, figure axes, and the decision the image
  supports.
- Keep source image paths or links when reinspection may matter; otherwise keep
  only the observation.
- For paper figures, capture axes, variables, baselines, units, evidence role,
  and limitation.
- For homework/problem images, preserve only the transcribed problem, uncertain
  symbols, assumptions, solution, and check.
- Do not store sensitive screenshots, account data, private messages, or raw
  third-party content.

## Long Task Pattern

Use a lean pipeline:

1. Triage: choose the relevant method file and context profile.
2. Scope: name the smallest context slice needed.
3. Retrieve: fetch independent sources in parallel when useful.
4. Compress: write a short synthesis with pointers.
5. Decide: answer, solve, implement, or ask one blocking question.
6. Verify: run the cheapest domain-appropriate check.
7. Escalate: read more, use heavier tools, or split work only when evidence
   requires it.

For a task that spans many turns, maintain a one-screen resume packet:

- objective and current subquestion
- active method/profile
- source pointers and artifacts
- accepted conclusions
- unresolved uncertainty or blocker
- next bounded action
- stop condition

## Open Method Index

These sources are conceptual anchors, not dependencies to install by default.

- ReAct: interleave reasoning, actions, observations, and updates for tasks
  needing tool checks.
  Source: https://arxiv.org/abs/2210.03629
- Tree of Thoughts: explore and compare multiple paths for hard planning or
  research questions.
  Source: https://arxiv.org/abs/2305.10601
- Reflexion: after failures, write compact reusable lessons instead of carrying
  long mistake history.
  Source: https://arxiv.org/abs/2303.11366
- Aider repo map: select repository context within a token budget.
  Source: https://aider.chat/docs/repomap.html
- Serena: symbol-level retrieval/editing to avoid unnecessary raw file reads.
  Source: https://github.com/oraios/serena
- LangChain contextual compression: retrieve broadly, pass forward only
  query-relevant content.
  Source: https://www.langchain.com/blog/improving-document-retrieval-with-contextual-compression
- LangGraph/Haystack: explicit state and pipeline routing for long workflows.
  Sources: https://github.com/langchain-ai/langgraph and
  https://github.com/deepset-ai/haystack

## User Preference

The user wants capable answers, not stingy answers. Be proactive about context
conservation while still spending tokens on verification, high-leverage
explanation, and the evidence needed for confidence.
