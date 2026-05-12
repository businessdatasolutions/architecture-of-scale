# Architecture of Scale

A small collection of brutalist visualisations about how language-model systems are actually architected — the substrates they read, the harnesses that orchestrate them, and the structural analogies to the computing patterns we already know.

## Visualisations

### 01 · Four ways to answer one question

A four-column comparison of context-architectures for LLM-based systems: **Context Window**, **RAG**, **Knowledge Graph**, and **LLM Wiki**.

Each architecture is shown processing the same three sample queries (common knowledge, proprietary &amp; recent, multi-hop relational), with deterministic visual indicators (`GROUNDED` / `PARTIAL` / `UNGROUNDED`) for where each one succeeds, partially answers, or breaks down.

- **English** &mdash; [`architecture-of-scale-en.html`](architecture-of-scale-en.html)
- **Nederlands** &mdash; [`architecture-of-scale-nl.html`](architecture-of-scale-nl.html)

### 02 · Same problems, same architecture

Two isometric motherboards side by side — the classical PC stack and the agent-harness stack — with synchronised pulses travelling along their PCB traces. Hover any component to reveal the function-level mapping: *memory management* ↔ *context management*, *scheduling* ↔ *agentic-loop control*, and so on. The harness *is* the operating system; the LLM *is* the CPU.

- **English** &mdash; [`harness-is-os-en.html`](harness-is-os-en.html)
- **Nederlands** &mdash; [`harness-is-os-nl.html`](harness-is-os-nl.html)

## Live versions

- **Landing page** &mdash; [`index.html`](index.html) (picks visualisation + language)
- Hosted on GitHub Pages: <https://businessdatasolutions.github.io/architecture-of-scale/>

Direct links:

- <https://businessdatasolutions.github.io/architecture-of-scale/architecture-of-scale-en.html>
- <https://businessdatasolutions.github.io/architecture-of-scale/architecture-of-scale-nl.html>
- <https://businessdatasolutions.github.io/architecture-of-scale/harness-is-os-en.html>
- <https://businessdatasolutions.github.io/architecture-of-scale/harness-is-os-nl.html>

## What's in visualisation 01

A3-landscape page with three horizontal bands and one bottom row:

1. **Header** &mdash; bulletin marker + mega title + a blue query block (top-right) that types the active sample query, with `Prev / Next / Replay` controls.
2. **Four vertical columns** &mdash; one per architecture, each with a substrate visualisation, an operation description, and a reply with status badge.
3. **Takeaway row** &mdash; one short interpretive line per column, dynamic per query.
4. **Investment axis** &mdash; from *less upfront work* to *more upfront work*, with the winning architecture's dot pulsing on each query.

### Animations

All animations are designed to make the *insightful gesture* of each column visible, not just decorative:

- **Column 01 (Context Window)** &mdash; matched training-memory tiles get a left-to-right blue fill sweep; post-cutoff tiles flash red when the active query crosses their boundary.
- **Column 02 (RAG)** &mdash; horizontal cosine-similarity bars grow from `0%` to score; top-3 fill in blueprint-blue; multi-hop queries highlight extraction-risk docs with an orange warning ring.
- **Column 03 (Knowledge Graph)** &mdash; typed edges along the retrieval path light up in blueprint-blue; on multi-hop queries an intersection-glow expands on the shared node (e.g. `headache`) when both branches converge.
- **Column 04 (LLM Wiki)** &mdash; matched entity-cards turn green and reveal their fields line-by-line; the timestamp `↻` does a small rotation to suggest freshness.

## What's in visualisation 02

Single-stage page with two isometric PCB motherboards in parallel:

1. **Header** &mdash; bulletin + byline + mega title `SAME PROBLEMS, SAME ARCHITECTURE.` + a blue manifesto block (top-right) carrying the canonical Karpathy-style quote, with `Pause / Replay` controls.
2. **Two motherboards** &mdash; identical PCB silhouette, identical component locations, different labels. Left: `APPLICATION / OS / CPU / RAM / DRIVERS / DISK`. Right: `PROMPT / HARNESS / LLM / CONTEXT WINDOW / TOOLS / EXTERNAL DB`.
3. **Six gutter arrows** &mdash; curved connectors between equivalent components, labels (`scheduler`, `compute`, `working memory`, `IO mediation`, `persistent store`, `program`) reveal on activation/hover.
4. **Detail panel** &mdash; on hover, the animation pauses and a panel below shows the second-order function-level mapping for that component pair.
5. **Takeaway row** &mdash; four short conclusions citing `agent-harness.md`.
6. **Timeline footer** &mdash; from `1969 · Multics` through `2026 · Codex / Cursor`.

### Animations

- **Continuous synchronised trace** &mdash; a pulse travels through the same path on both boards simultaneously, using `pathLength` motion along the PCB traces. The two boards flicker as one — the visual claim is structural isomorphism, not comparison.
- **Component activation** &mdash; blue fill sweep on the top face of each component as the pulse arrives.
- **Hover-paused mapping** &mdash; hover one component on either board to highlight its equivalent on the other, with stronger glow on the gutter arrow that connects them.

## Stack

- Pure HTML &middot; no build step, no server
- React 18 + motion.dev 11 (loaded via esm.sh CDN)
- Inter + JetBrains Mono + Instrument Serif (Google Fonts)
- Respects `prefers-reduced-motion`

## How to view locally

Open any of the HTML files directly in a modern browser. No server required.

```sh
open index.html
# or pick a specific visualisation:
open architecture-of-scale-en.html
open harness-is-os-en.html
```

Best viewed on viewports ≥ 1280 px (each page sets `min-width: 1280px`; horizontal scroll appears on smaller screens).
