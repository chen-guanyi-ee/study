# Paper Reading And Annotated HTML Method

Load this file when the user asks for paper annotation, a paper guide, bilingual reading notes, argument analysis, or an HTML/PDF study artifact.

## Goal

Reveal the paper's argument structure, not only its content. Help the user see how the paper moves from problem framing to thesis, method, evidence, limitations, rebuttal, and conclusion.

The user especially wants paper-reading mode to compensate for incomplete questions. If the user asks about only one paragraph, figure, result, or claim, still infer the larger research question it belongs to and explain the local detail in that broader frame.

Token discipline matters in paper mode. For ordinary questions, read only the relevant sections, figures, tables, abstract, and conclusion before expanding. Full annotated HTML is intentionally heavier and should be used when the user asks for that artifact.

Use a paper-QA pipeline for ordinary questions: define the question, locate evidence, gather only relevant passages/figures/tables, synthesize the answer, then perform a Chinese interpretation review.

When creating a heavier reading artifact, borrow the useful parts of `nature-reader` without installing or loading the whole external skill by default: keep a source map, put figures/tables near the first substantive discussion, and record translation/terminology uncertainty separately.

## Question Thinking Pipeline

Before answering a paper question, infer the task type:

- Comprehension: what does this paragraph/equation/figure mean?
- Argument: what claim is this evidence supporting?
- Method: what is the mechanism, model, circuit, architecture, algorithm, or experiment?
- Validity: is the evidence measured, simulated, modeled, or assumed?
- Comparison: what baseline or prior work is being beaten, and on which metric?
- Reproduction: what would be needed to implement, simulate, verify, or reproduce it?
- Research taste: what is the interesting next question, weakness, or ablation?

Then answer at that level instead of only translating the local text.

## Default Artifact

- Create a single `.html` file unless the user asks otherwise.
- Use Traditional Chinese for explanations and translations.
- Preserve original English text, with fluent academic Chinese paraphrase/translation under each English paragraph.
- For research notes or Markdown output, prefer this compact bundle when useful:
  - `paper.md`: argument-aware reading notes in Traditional Chinese, with selected English anchors.
  - `source_map.json` or a small source table: section/page/figure/table/equation anchors for important claims.
  - `translation_notes.md`: terminology choices, ambiguous phrases, and claims that should not be strengthened in Chinese.
  - `assets/`: only figures/tables/images that are needed for reasoning or presentation.

## Required Structure

1. Top navigation bar
   - paper title and course/context information
   - color legend:
     - yellow = core thesis / central claim
     - red = key concept / terminology
     - blue = empirical evidence / data
     - green = concession / limitation / rebuttal handling
     - purple = methodology explanation
2. Sticky section navigation with jump links.
3. Main body with two columns:
   - left: English-Chinese bilingual paragraphs
   - right: figures, tables, or image placeholders tied to the relevant paragraph
4. Bottom argument overview:
   - problem -> thesis -> method -> evidence -> limitations/rebuttal -> conclusion
   - one-sentence central claim
   - strongest part of the argument
   - weakest part of the argument

## Paragraph Format

Each paragraph should include:

1. English original
   - Lora serif font
   - highlight only argumentative or structurally important spans
2. Thin divider
3. Traditional Chinese paraphrase/translation
   - fluent academic style
   - no highlight colors
   - light beige background `#f0ece2`
   - thin left vertical border

## Right Column

For each paragraph or local paragraph group, show all referenced figures/tables/images. If the paper image is unavailable, create a clear placeholder with:

- figure/table number
- caption or inferred role
- what claim/evidence it supports
- what the reader should notice

Do not let visuals become decorative; explain their argumentative role.

For figure/table-heavy papers, treat visual evidence as first-class context: identify axes, variables, baselines, units, measurement setup, and what conclusion the visual can and cannot support.

Place a figure/table near the first paragraph where it materially supports the argument, not only where the paper originally references it. Preserve the original figure/table number and caption anchor so later claims remain traceable.

## Design Style

- deep navy top navigation
- warm paper/off-white page background
- Lora for paper text
- IBM Plex Sans for UI/navigation/labels
- color-coded highlights
- annotation cards with colored left borders
- responsive single-column mobile layout

## Interpretation Rules

- Prioritize argument logic over exhaustive translation.
- Build a claim-to-evidence map for important claims: claim -> source location -> evidence type -> limitation.
- Identify each paragraph's role: problem setup, thesis, method, evidence, comparison, limitation, rebuttal, or conclusion.
- Add task reasoning before answering: what is the user likely trying to decide or understand, what concept is missing, and what would be the highest-leverage explanation?
- When a question is underspecified, answer the most useful inferred version and state the assumption briefly.
- Use demand prediction: after the main answer, optionally add one compact follow-up question or "next thing to check" if it would expose the paper's core contribution, weakness, or implementation consequence.
- For difficult claims, compare at least two plausible interpretations before choosing the best-supported one.
- For IC papers, connect claims to architecture, circuit, memory/data movement, process node, measurement setup, and metrics.
- Distinguish measured silicon evidence from simulation, modeling, or design rationale.
- Compress intermediate notes into problem -> thesis -> method -> evidence -> limitation instead of carrying raw copied paper text.
- Ground claims in cited paper locations when possible: section, paragraph, equation, figure, table, or experiment.
- For each important claim, ask internally: what is the evidence, what is the hidden assumption, what metric matters, and what would falsify it?

## Research Review Gate

For paper guides, proposal drafts, or manuscript-like material, run a compact reviewer-style pressure test inspired by `nature-reviewer`:

- Reviewer A: novelty and positioning; what prior work could make the claim look less new?
- Reviewer B: technical soundness; where do assumptions, methodology, statistics, circuits, simulations, or verification fail?
- Reviewer C: reader value; who should care, and what story/figure/result would convince them?
- Synthesis: output only consensus risks, important disagreements, and the strongest next fix. Do not print three long fake reviewer reports unless the user explicitly asks.

Each serious criticism should include a pointer to the claim/evidence location or state that it is an inference from missing evidence.

## Traditional Chinese Review

For Chinese explanations, perform a compact review before finalizing:

- Faithfulness: preserve the technical meaning; do not over-translate a claim into something stronger.
- Terminology: keep common technical terms stable; preserve original English term in parentheses when ambiguity is likely.
- Argument role: explain whether the sentence is claim, method, evidence, limitation, or comparison.
- Domain bridge: for IC/architecture papers, connect the explanation to workload, dataflow, memory/interconnect, circuit/process, measurement, and verification when relevant.
- Brevity: avoid ornate prose. Use clear academic Traditional Chinese.

## File Naming

Use a concise descriptive filename based on the paper title, for example:

`A_28nm_64_5_annotated.html`

Prefer self-contained HTML when possible.

## Open Method Index

Use these as conceptual anchors, not dependencies to install by default:

- PaperQA2: scientific-paper RAG pattern: search, gather evidence, and answer with cited sources.
  Source: https://github.com/Future-House/paper-qa
- LlamaIndex: document agents and routing over PDFs/data; useful mental model for selecting relevant sections before synthesis.
  Source: https://github.com/run-llama/llama_index and https://developers.llamaindex.ai/python/framework/
- Haystack: modular RAG pipeline with retrieval, routing, ranking, and generation components.
  Source: https://github.com/deepset-ai/haystack
- SPIQA: scientific paper image/question answering benchmark emphasizing figures and tables as reasoning objects.
  Source: https://github.com/google/spiqa
- nature-skills / nature-reader: source-map based bilingual reading material with figure/table placement and translation notes.
  Source: https://github.com/Yuan1z0825/nature-skills/tree/main/skills/nature-reader
- nature-skills / nature-reviewer: simulated pre-submission review emphasizing novelty, significance, technical soundness, readability, claim/evidence pointers, and cross-review synthesis.
  Source: https://github.com/Yuan1z0825/nature-skills/tree/main/skills/nature-reviewer
