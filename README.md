# Architecture of Scale

Brutalist-blueprint visualisation comparing four context-architectures for LLM-based systems: **Context Window**, **RAG**, **Knowledge Graph**, and **LLM Wiki**.

Each architecture is shown processing the same three sample queries (common knowledge, proprietary &amp; recent, multi-hop relational), with deterministic visual indicators (`GROUNDED` / `PARTIAL` / `UNGROUNDED`) for where each one succeeds, partially answers, or breaks down.

## Live versions

- **Landing page** &mdash; [`index.html`](index.html) (chooses language)
- **English** &mdash; [`architecture-of-scale-en.html`](architecture-of-scale-en.html)
- **Nederlands** &mdash; [`architecture-of-scale-nl.html`](architecture-of-scale-nl.html)

Hosted on GitHub Pages:

- <https://businessdatasolutions.github.io/architecture-of-scale/> &mdash; landing page
- <https://businessdatasolutions.github.io/architecture-of-scale/architecture-of-scale-en.html>
- <https://businessdatasolutions.github.io/architecture-of-scale/architecture-of-scale-nl.html>

## What's in each visualisation

A3-landscape page with three horizontal bands and one bottom row:

1. **Header** &mdash; bulletin marker + mega title + a blue query block (top-right) that types the active sample query, with `Prev / Next / Replay` controls.
2. **Four vertical columns** &mdash; one per architecture, each with a substrate visualisation, an operation description, and a reply with status badge.
3. **Takeaway row** &mdash; one short interpretive line per column, dynamic per query.
4. **Investment axis** &mdash; from *less upfront work* to *more upfront work*, with the winning architecture's dot pulsing on each query.

## Animations

All animations are designed to make the *insightful gesture* of each column visible, not just decorative:

- **Column 01 (Context Window)** &mdash; matched training-memory tiles get a left-to-right blue fill sweep; post-cutoff tiles flash red when the active query crosses their boundary.
- **Column 02 (RAG)** &mdash; horizontal cosine-similarity bars grow from `0%` to score; top-3 fill in blueprint-blue; multi-hop queries highlight extraction-risk docs with an orange warning ring.
- **Column 03 (Knowledge Graph)** &mdash; typed edges along the retrieval path light up in blueprint-blue; on multi-hop queries an intersection-glow expands on the shared node (e.g. `headache`) when both branches converge.
- **Column 04 (LLM Wiki)** &mdash; matched entity-cards turn green and reveal their fields line-by-line; the timestamp `↻` does a small rotation to suggest freshness.

## Stack

- Pure HTML &middot; no build step, no server
- React 18 + motion.dev 11 (loaded via esm.sh CDN)
- Inter + JetBrains Mono + Instrument Serif (Google Fonts)
- Respects `prefers-reduced-motion`

## How to view locally

Open any of the HTML files directly in a modern browser. No server required.

```sh
open architecture-of-scale-en.html
# or
open architecture-of-scale-nl.html
```

Best viewed on viewports ≥ 1280 px (the page has a `min-width: 1280px`; horizontal scroll appears on smaller screens).
