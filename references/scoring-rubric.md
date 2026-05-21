# Scoring rubric — calibrated examples

Used in **Stage 7 (Evaluate)**. The goal: produce honest, comparable scores across many solutions. Bad scoring is the #1 way this pipeline fails — if everything scores >0.8, the ranking is useless.

## Combined score formula

```
combined = 0.15·novelty
         + 0.25·verified_novelty
         + 0.15·surprise
         + 0.20·feasibility
         + 0.15·structural_depth
         + 0.10·actionability

if source_domain == home_domain (case-insensitive after trim):
    combined *= 0.5
```

Verified novelty is weighted highest because it's the hardest to fake — it comes from checking against real existing work.

---

## Dimension 1: Novelty (0.0–1.0)

How surprising/non-obvious is the analogy itself? Domain distance matters but isn't the whole story.

| Score | Description | Example |
|-------|-------------|---------|
| 0.0–0.3 | Obvious connection, same general field | "Use a database index to speed up search — same field, obvious technique." |
| 0.3–0.5 | Familiar cross-field connection | "Use neural networks to classify images — well-trodden ML application." |
| 0.5–0.7 | Interesting cross-field connection | "Apply ant colony foraging to traffic routing — known but not obvious." |
| 0.7–0.85 | Surprising, distant domain connection | "Apply slime-mold network optimization to Tokyo rail (Tero et al.) — distant, validated, non-obvious." |
| 0.85–1.0 | Genuinely novel, paradigm-shifting | "Treat city heat resilience as an immune-tolerance topology problem — no prior published treatment." |

## Dimension 2: Verified novelty (0.0–1.0)

How does it score against actual existing work? Set in Stage 6 (Verify); carried into Stage 7.

| Score | Meaning |
|-------|---------|
| 0.0–0.2 | This exact approach is well-known and widely used |
| 0.2–0.4 | Close variants exist, this is a minor twist |
| 0.4–0.6 | Related approaches exist; this combines elements in a new way |
| 0.6–0.8 | Genuinely novel combination or transfer; not previously attempted as a unit |
| 0.8–1.0 | No known similar approach |

**Watch out:** if verified_novelty < 0.4, run the Push phase in Stage 6 before final ranking.

## Dimension 3: Surprise (0.0–1.0)

How much would this shift a domain expert's beliefs about what's possible? Different from novelty — surprise asks *would this make an expert sit up*.

| Score | Description | Example |
|-------|-------------|---------|
| 0.0–0.3 | Confirms existing assumptions | "Yes, redundancy improves reliability — known." |
| 0.3–0.6 | Interesting twist on known approach | "Use redundancy at a different layer than usual." |
| 0.6–0.8 | Would make an expert reconsider their approach | "Reliability via deliberate component fragility plus rapid replacement." |
| 0.8–1.0 | Paradigm-shifting | "Cooling is the wrong goal — design for thermal indifference at 55°C using biological precedents." |

## Dimension 4: Feasibility (0.0–1.0)

How practically implementable? Be honest. Most exciting cross-domain ideas score 0.3–0.6 — that's normal.

| Score | Description | Example |
|-------|-------------|---------|
| 0.0–0.3 | Interesting metaphor but impractical | "Use general relativity time dilation to extend project deadlines." |
| 0.3–0.6 | Requires significant adaptation, possible | "Build a passive ventilated geopolymer panel with shape-memory-alloy valves." |
| 0.6–0.8 | Clearly transferable with moderate effort | "Apply a known PID controller pattern from chemical engineering to API rate limiting." |
| 0.8–1.0 | Ready to implement | "Add exponential backoff with jitter to retry loops — library exists." |

## Dimension 5: Structural depth (0.0–1.0)

Quality of the relational mapping in Stage 4. The mapping count and chain structure mostly determine this — don't second-guess.

| Score | Description |
|-------|-------------|
| 0.0–0.3 | Surface-level analogy, ≤2 mappings, all structural |
| 0.3–0.5 | 3–4 mappings, mostly structural/functional, no causal chain |
| 0.5–0.7 | 4–5 mappings, at least one causal chain of 2 |
| 0.7–0.85 | 5–7 mappings, at least one chain of 3 connected causal/process relations |
| 0.85–1.0 | 6+ mappings, multiple interlocking chains, predicts non-obvious failure modes |

## Dimension 6: Actionability (0.0–1.0)

How concrete are the steps? Look at `concrete_approach`.

| Score | Description |
|-------|-------------|
| 0.0–0.3 | Vague inspiration, unclear next steps |
| 0.3–0.5 | General direction clear, significant design work needed |
| 0.5–0.7 | Numbered steps present but some hand-waving on materials/parameters |
| 0.7–0.85 | Concrete numbered steps with specific materials, parameters, and quantities; could prototype |
| 0.85–1.0 | Ready-to-implement plan with sources, suppliers, and measurement protocols |

---

## Calibration sanity-check

After scoring all solutions, check the **distribution**:

- If >30% of solutions score combined >0.7, you're under-critical. Push some down.
- If <10% score combined >0.5, you're over-critical. Reconsider the floor.
- The top-ranked solution should be **clearly distinguishable** from the median by at least 0.10 combined points.
- The **standard deviation** of combined scores across 20+ solutions should be ≥0.08. Tighter than that means you're not differentiating.

## Heuristic fallback (if LLM scoring fails)

If you can't produce a confident score for a dimension, use this back-of-envelope:

- **Novelty** = `0.3 × domain_distance + 0.2 × abstraction_bonus` clipped to [0,1]
- **Feasibility** = `{strong: 0.8, moderate: 0.5, weak: 0.3}[transfer_strength]`
- **Structural depth** = `min(1, mapping_count / 7) × (1 + 0.2 × has_causal_chain)`
- **Actionability** = 0.5 (default) unless steps are explicitly enumerated

Where:
- `domain_distance` = 0.0 (identical), 0.3 (same category), 0.5 (adjacent), 0.8 (distant) per `domain-catalog.md`
- `abstraction_bonus` = `{effect: 0.2, phenomenon: 0.15, action: 0.1, parts: 0.0}`
