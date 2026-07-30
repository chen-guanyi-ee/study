# Problem Solving

Load when the user asks for homework/exam-style solving, derivation, design
calculation, or rigorous technical explanation across math, circuits,
electronics, IC design, electromagnetics, signals, controls, architecture, or
adjacent engineering topics.

## Contract

Solve the actual problem with enough rigor to be trusted:

1. Transcribe or restate the problem, including assumptions.
2. Choose the method and state the governing law/model/convention.
3. Derive with explicit variables, units, signs, domains, and constraints.
4. Give the final answer in the requested form.
5. Include a compact but real check.

Use Traditional Chinese labels when the conversation is in Chinese. Keep the
answer concise, but never hide a step that carries sign, unit, boundary,
approximation, or model-assumption risk.

## Image Inputs

- Transcribe visible text/equations first.
- Mark uncertain symbols, units, limits, signs, subscripts, and node labels.
- Ask only if ambiguity changes the answer; otherwise state the assumption and
  continue.

## Mutual Review Gate

Before finalizing, silently run four mutually adversarial passes:

- Solver: direct solution path and equations.
- Checker: algebra, units, dimensions, signs, boundary/initial conditions,
  domains, and final form.
- Skeptic: traps such as invalid cancellation, wrong convention, hidden ideal
  assumption, off-by-one timing, unstable pole, wrong region, or impossible
  limiting behavior.
- Arbiter: resolves conflicts and keeps only the useful caveat or correction in
  the answer.

Do not print the debate transcript. The final answer must reflect it.

## Required Checks

Always include one `Check` unless the user explicitly asks for only a hint.
Choose the strongest lightweight check:

- Math: substitute back, differentiate/integrate inverse, check dimensions,
  normalization, limiting case, or numeric spot check.
- Circuits/electronics/IC: KCL/KVL, sign/reference direction, operating region,
  small-signal vs large-signal boundary, units, limiting input/device case,
  gain/resistance consistency, timing/noise/power sanity.
- Electromagnetics: coordinate system, boundary conditions, units, direction,
  symmetry, far-field/quasi-static assumption, limiting distance/frequency.
- Signals/controls/communications: transform convention, ROC/causality,
  initial/final value, poles/stability, sampling/update recurrence, units.
- Computer architecture/digital design: bit width, address/tag/index fields,
  CPI/latency/throughput units, pipeline hazards, FSM edges, cache cases,
  timing path or critical path consistency.

## Domain Discipline

- Electronics/IC: separate DC bias, small-signal, transient, noise, power, and
  layout/timing assumptions. Do not mix models without saying so.
- Engineering math: define variables/support/domains; apply theorem conditions
  before using Green/Stokes/Gauss, transforms, diagonalization, or probability
  identities.
- Architecture/digital: identify abstraction level first: ISA, datapath,
  pipeline, cache/memory, RTL, timing, or physical implementation.
- Approximation: name what is ignored and check whether the ignored term could
  dominate.

## Tool Use

Use tools only when they materially reduce error:

- SymPy/Python: symbolic algebra, integrals/derivatives, linear algebra,
  transforms, equation solving, numeric spot checks.
- SPICE/ngspice mental model: circuit operating point, AC/transient sanity, and
  model-region checks.
- Yosys/ABC mental model: Boolean equivalence, FSM/logic simplification, and
  RTL-level counterexample thinking.
- OpenSTA mental model: setup/hold, critical path, clock constraint, and timing
  slack reasoning.
- Web: only for current standards, datasheets, tool behavior, tables, or when
  the user asks to look something up.

## Output Shape

Default:

```text
Problem:
...

Solution:
1. ...
2. ...

Answer:
...

Check:
...
```

For simple questions, compress to `Solution / Answer / Check`. For conceptual
or essay questions, use `Key idea / Reasoning / Answer / Check or caveat`.

## Valuable Anchors

- Polya, *How to Solve It*: understand, plan, execute, look back.
- SymPy: symbolic mathematics and exact/numeric checks.
  https://www.sympy.org/ and https://github.com/sympy/sympy
- Lean/mathlib: proof hygiene, assumptions, theorem conditions, exactness.
  https://lean-lang.org/use-cases/mathlib/ and
  https://github.com/leanprover-community/mathlib4
- ngspice: open-source SPICE circuit simulation mental model.
  https://ngspice.sourceforge.io/
- Yosys/ABC: RTL/logic synthesis and verification mental model.
  https://github.com/YosysHQ/yosys and https://github.com/berkeley-abc/abc
- OpenSTA: static timing verification mental model.
  https://github.com/The-OpenROAD-Project/OpenSTA
