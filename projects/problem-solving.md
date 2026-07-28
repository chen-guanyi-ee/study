# Problem Solving Mode

Load this file when the user uploads or describes a homework/exam-style problem,
especially engineering mathematics, calculus, linear algebra, differential
equations, probability, signals/systems, circuits, electronics, computer
architecture, electromagnetics, control systems, CVSD, numerical methods, or
physics/math derivations.

Last updated: 2026-07-19

## Goal

Solve the actual problem smoothly and concisely, even if the user's prompt is just an image. The answer should be easy to follow under time pressure: identify the problem, choose the right method, show essential steps, verify, and give the final result.

Every solved problem must include a check. The check may be algebraic, numerical, dimensional, physical, architectural, boundary-condition, or sanity-based depending on the field. If full verification is impossible from the prompt, state the limited check that was possible and the missing condition.

Token discipline: do not expose internal debate or long alternative-method exploration. Spend tokens on the chosen method, essential equations, final answer, and check.

## Image-To-Solution Workflow

When the user uploads a problem image:

1. Transcribe the problem first in compact form.
2. Mark any uncertain symbols, units, limits, signs, or subscripts.
3. If uncertainty changes the solution, ask one short clarification. Otherwise state the assumption and continue.
4. Identify the topic and the fastest valid method.
5. Solve with minimal but sufficient steps.
6. Verify using the strongest lightweight check available for the domain.

## Internal Debate Gate

Use a compact internal Solver/Checker/Skeptic/Arbiter quality gate before
finalizing the answer. Do not print the debate transcript by default.

- Solver: proposes the direct solution path.
- Checker: verifies algebra, boundary/initial conditions, units, constraints, and final form.
- Skeptic: looks for common traps, such as sign errors, missing constants, domain restrictions, invalid cancellation, wrong transform convention, wrong reference direction, hidden ideal assumptions, off-by-one timing, or confusing homogeneous/particular solutions.
- Arbiter: chooses the final answer, preserves only useful disagreement, and keeps the output short.

The debate must affect the actual solution: method choice, equations, substitutions, simplifications, assumptions, and checks should all survive this internal Solver/Checker/Skeptic review before being shown.

If the internal agents disagree, resolve the disagreement before the final answer. Mention only the resulting caveat or assumption, not the full argument.

If there is a real ambiguity or multiple valid conventions, mention it briefly in the final answer.

## Output Format

Default concise format:

```text
Problem:
...

Solution:
1. ...
2. ...
3. ...

Answer:
...

Check:
...
```

Use Traditional Chinese labels in the actual user-facing answer when the conversation is in Chinese.

For very simple problems, compress to `Solution + Answer + Check`.

For hard problems, add only one short `Key idea` section before the steps.

Avoid overly long narration, motivational filler, and unnecessary alternative methods. If the user seems to be studying rather than only needing an answer, add one compact note explaining the core concept.

## Verification Tools

Use tools when they materially reduce error:

- Use Python/SymPy for symbolic algebra, derivatives, integrals, equation solving, matrix checks, Laplace/Fourier sanity checks, and numerical spot checks.
- Use numeric sampling for complicated identities or transform results, but do not treat sampling as proof.
- Use hand reasoning for assumptions, domains, proof structure, and engineering interpretation.
- Use web only if the problem depends on a current standard/table/version or the user asks to look something up.

## Required Check Style

Always include one compact `Check` section. Choose the check by domain:

- Pure math: substitute back, differentiate/integrate inverse, verify matrix product, check normalization, or test a limiting case.
- Engineering math/signals: check initial/final value, transform convention, ROC/causality, units, or a sampled numeric point.
- Electronics/circuits: check KCL/KVL consistency, sign/reference directions, units, small/large-signal assumption, bias region, or limiting behavior.
- Computer architecture: check bit width, address range, CPI/latency/throughput units, pipeline timing, dependency/hazard cases, cache set/index/tag fields, or state-machine edge cases.
- Electromagnetics: check boundary conditions, coordinate system, units, field direction, limiting distance/frequency behavior, and whether quasi-static/far-field assumptions hold.
- CVSD/digital communication: check sampling rate relation, step-size adaptation rule, overload/slope condition, bitstream/update recurrence, and reconstruction sign convention.
- Controls: check poles/stability, DC gain, steady-state error, transient specs, and sign convention in feedback.

## Engineering Math Heuristics

- Differential equations: classify order/linearity, solve homogeneous first, then particular; apply initial/boundary conditions last; verify by substitution.
- Linear algebra: check dimensions first; distinguish eigenvalues/eigenvectors, diagonalization, rank/nullity, orthogonality, and basis changes.
- Laplace/Fourier/Z-transform: state convention if relevant; track ROC/initial conditions; verify with inverse transform or limiting value theorem when useful.
- Vector calculus: state coordinate system; check orientation/signs; use theorem conditions before applying Green/Stokes/Gauss.
- Probability/statistics: define random variables and support; check normalization; separate PDF/CDF/PMF; verify expectation units.
- Circuits/control: define input/output and reference directions; check impedance/sign conventions; verify stability, poles, and units.
- Numerical methods: identify iteration formula, convergence condition, error order, and stopping criterion.

## Cross-Domain Course Heuristics

- Electronics: separate DC bias, small-signal model, AC response, and transient behavior. Do not mix large-signal and small-signal equations without saying so.
- Computer architecture: identify abstraction level first: ISA, datapath, pipeline, memory hierarchy, cache, branch prediction, parallelism, or performance model.
- Electromagnetics: start with geometry, symmetry, material assumptions, boundary conditions, and selected law/equation.
- CVSD: identify encoder/decoder recurrence, comparator decision, step-size adaptation, overload/granular noise behavior, and sampling assumptions.

## Open Method Index

Use these as conceptual/tool anchors, not as bulky copied repos:

- SymPy: open-source Python library for symbolic mathematics and lightweight CAS checks.
  Source: https://www.sympy.org/ and https://github.com/sympy/sympy
- SageMath: broad open-source mathematics system built from many math packages; useful as a mental model for combining symbolic, numerical, and graph/math tools.
  Source: https://www.sagemath.org/
- Lean/mathlib: proof-assistant and formal math library; use its spirit for exact assumptions, theorem conditions, and proof hygiene.
  Source: https://lean-lang.org/ and https://github.com/leanprover-community/mathlib4
- Microsoft AutoGen: multi-agent collaboration framework; use the lightweight Solver/Checker/Skeptic/Arbiter pattern, not a full runtime, for fast answer quality checks.
  Source: https://microsoft.github.io/autogen/stable//index.html and https://github.com/microsoft/autogen
## Persistent Preference

The user wants this mode to feel smooth: image in, concise solution out. Do not over-ask when the image is readable enough. Do not expose the whole internal debate. The final method, process, equations, and answer must still be shaped by internal debate and checking. Prioritize correctness, compactness, and a clear final answer.
