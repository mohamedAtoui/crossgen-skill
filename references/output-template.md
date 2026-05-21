# Output template — final report

Use this template for the user-facing report at the end of a CrossGen run. Adapt verbatim — including the section ordering — so output is consistent across runs.

---

```markdown
# CrossGen — <one-line problem title>

## Problem

> <original problem statement, blockquoted verbatim>

## Pipeline configuration

- **Mode:** full (9 stages) | quick (5 stages, no verify/evolve)
- **Parallel paths:** <N> (original + <N-1> reframings)
- **Total solutions before dedup:** <X>
- **After deduplication:** <Y>
- **Solutions verified novel (≥0.5):** <Z>
- **Solutions pushed:** <P>
- **Evolved variants:** <E>
- **Final ranked solutions:** <F>
- **Average verified novelty:** <0.XX>
- **Top combined score:** <0.XX>

## Reformulations

### Original (Path 1)

> <original problem>

### <Technique> (Path 2 — divergence: 0.XX)

> <reframed problem statement>

*Why this opens a different space:* <reasoning>

### <Technique> (Path 3 — divergence: 0.XX)

> <reframed problem statement>

*Why this opens a different space:* <reasoning>

> *Not selected as paths: <other 3 reframings, one-line each>*

## Problem decomposition (primary path)

- **Home domain:** <domain>
- **Primary function:** <domain-neutral statement>
- **Key contradictions:**
  1. <improving> ↔ <worsening>: <natural-language>
  2. …
- **Behavior chain:** <step1> → <step2> → … → <final>
- **Leverage points:**
  - <description> (<meadows_level>) — <why high leverage>

## Abstractions

| Lens | Output |
|------|--------|
| SAPPhIRE | Effect: <…>; Phenomenon: <…> |
| Biologize | <3 of the most useful nature questions> |
| WordTree | <3 of the most useful cross-domain bridge terms> |
| TRIZ | <matched principles, e.g. "11, 35, 27, 28"> |

## Candidate domains explored

| Domain | Distance | Lens | Rationale |
|--------|----------|------|-----------|
| <domain> | high | biologize | <one-line: which mechanism in mind> |
| … | | | |

---

# Top 10 solutions (ranked)

For each, follow this block:

## #N — <Source domain> → <Source mechanism> [Path N | Evolved?] (Score: 0.XX)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.XX | 0.XX | 0.XX | 0.XX | 0.XX | 0.XX | **0.XX** |

**Mechanism:** <one-paragraph description of the source-domain mechanism>

**Structural mapping (key correspondences):**
- <source element> ↔ <target element> (<relation type>)
- … (3–5 key mappings; full list in appendix)

**Concrete approach:**

Step 1 — <action with specific materials/parameters>: <details>

Step 2 — <action>: <details>

Step 3 — <action>: <details>

[continue numbered steps]

**Candidate inferences (predictions from the source):**
- <non-obvious prediction the source domain makes about the target>
- …

**Testable predictions:**
- <falsifiable prediction with quantitative threshold and how to measure>
- …

**Where the analogy breaks:**
- <weak spot 1>
- <weak spot 2>
- <weak spot 3>

**Feasibility notes:** <practical next steps someone could take this week>

**Research pointers:**
- Scholar: `<search query 1>`
- Scholar: `<search query 2>`
- Key terms: <term 1>, <term 2>, <term 3>
- Seminal works (if confident): <citation>

---

# Diagnostics & honesty

- **Quality warnings:** <list any quality-gate warnings from the pipeline, or "none">
- **Failed candidate domains** (insufficient mappings, retried/skipped): <list, or "none">
- **Solutions pushed in Stage 6** (low initial novelty, rewritten): <indices or "none">
- **Same-domain penalty applied to:** <indices or "none">

# Where this output is itself weak

(self-critique — what to push back on)

- <how the framing of the problem might have biased the analogies>
- <what important domains we did NOT explore and why>
- <what kind of additional research would strengthen the top 3>
```

---

## Notes on formatting

- **Always show all 6 dimension scores** in the per-solution table. Hiding "low" dimensions inflates the apparent quality.
- **Always include "where it breaks"** for each top solution. Skipping it converts rigorous analogy into inspiration porn.
- **Show ranked-but-not-top solutions** too (positions 11+ in a compact list with just name + score). Future-you may want to revisit them.
- **The diagnostics section is non-negotiable.** Pipeline honesty is part of the value.
- **The final self-critique section is non-negotiable.** If you can't think of a weak spot in your own output, you haven't been honest enough.

## Length guidance

- Problem + decomposition: ~400 words
- Each top-10 solution: 300–600 words (top 3 get more detail than 8–10)
- Total report: 5,000–12,000 words for a meaty problem; 2,000–4,000 for quick mode
- Truncate `mechanism` descriptions and step details if running out of context — but never truncate `where_it_breaks` or `key_predictions`. Those are the load-bearing parts.
