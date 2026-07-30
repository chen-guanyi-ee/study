# Paper Reading

Load when the user asks for paper explanation, figure/table interpretation,
annotation HTML, reading notes, argument analysis, or paper-based research.

## Default Flow

1. Identify the local question: comprehension, method, evidence, comparison,
   validity, reproduction, or research taste.
2. Read the smallest useful set: title/abstract, relevant figures/tables,
   conclusion, then exact sections.
3. Explain the paper's logic: problem -> method -> evidence -> limitation.
4. For IC papers, connect claims to architecture, dataflow, memory, arithmetic,
   control, process node, measurement, and metrics.
5. Distinguish measured silicon, simulation, modeling, and inference.

## Annotated HTML

Default artifact is a single `.html` file with only the central reading body:

- No title/header, course info, reading tips, sticky bars, navigation, color
  legend, or bottom overview.
- Two columns: left = English anchor paragraph plus explanation notes; right =
  exact cropped figure/table/equation image.
- Highlight only red terms and purple methods/mechanisms.
- No paragraph-level translation. Explain only highlighted red/purple items in
  concrete English digital-IC terms.
- Each highlighted item needs a substantial explanation: what it means, which
  hardware/dataflow/memory/arithmetic/control/timing/area/energy issue it
  touches, and how the paper uses it.

## Figure Rules

- Crop multi-figure pages to the exact relevant panel; avoid whole pages unless
  the whole page is being discussed.
- Right-column images have no extra title or caption text.
- The rendered HTML must show the whole crop: no fixed-height wrappers,
  `object-fit: cover`, negative margins, or overflow hiding.
- Check both the crop file and the browser-visible image. If uncertain, widen
  the crop and note uncertainty in the left-column explanation.

## Chinese Review

When using Chinese, keep terminology stable, preserve technical meaning, and do
not strengthen claims beyond the evidence.
