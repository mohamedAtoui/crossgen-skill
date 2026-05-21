# Structure-Mapping Theory — operational rules

Read this before running Stage 4 (Mine). It is the single most important reference in the skill.

## The core claim (Gentner, 1983)

> Analogy is the mapping of **relational structure** from a base domain to a target domain.

Not the mapping of *objects*. Not the mapping of *attributes*. The mapping of **relations between objects** — and especially **systems of relations**.

This is why "atom is like the solar system" is a real analogy and "watermelon is like the planet Earth (both are round)" is not. The first maps the relation `revolves-around(electron, nucleus) → revolves-around(planet, sun)`. The second maps a surface attribute.

## Two principles you must enforce

### 1. Map relations, not surface features

When you produce a mapping in Stage 4, ask of each pair:

> "If I removed all the labels and just looked at the abstract relation, would the source's relation still hold in the target?"

| BANNED (surface) | REQUIRED (relational) |
|------------------|----------------------|
| "Both have networks." | `inhibits(neuron_A, neuron_B) ↔ rate-limits(service_A, service_B)` |
| "Both have feedback." | `gain_decreases_as(output, target) ↔ throttle_engages_as(latency, SLO)` |
| "Both are systems." | (no — too vague to map at all) |
| "Cells and microservices." | `replicates_under(cell_lineage, growth_signal) ↔ scales_under(deployment, load_signal)` |

If your mapping reads like "both X and Y have Z", you are mapping attributes. Rewrite it as a verbed relation between two specific entities.

### 2. The systematicity principle

Higher-order relations (relations *between* relations) carry more analogical weight than isolated lower-order matches. A connected chain of three relations is worth more than five disconnected matches.

So when you build your `mappings` array, **prefer chains**:

```
[step1 causes step2]      ↔  [step1' causes step2']
[step2 enables step3]     ↔  [step2' enables step3']
[step3 constrains step4]  ↔  [step3' constrains step4']
```

This gives Gentner's "candidate inference": once the chain is mapped, predictions from the base domain *transfer automatically* to the target. That's where novel falsifiable predictions come from.

## Relation types — pick one per mapping

| Type | Definition | Example |
|------|-----------|---------|
| `causal` | A causes B | "ventricle contraction → arterial pressure rise" |
| `functional` | A is for the purpose of B | "smooth-muscle dilation serves local oxygen demand" |
| `structural` | A is part of / contained in B | "capillary bed branches off arteriole" |
| `constraint` | A bounds / limits B | "viscosity at low flow → flow stagnation" |
| `process` | A is a step in process B | "venous return is the preload phase of next stroke" |

Prefer `causal` and `process` over `structural` — they carry more transfer power.

## Quality checklist (apply per analogy in Stage 4)

A `StructuralAnalogy` passes if **all** of the following hold:

- [ ] The mechanism named is **a specific real thing** — a named phenomenon, not a vague concept ("baroreceptor reflex" not "feedback in biology")
- [ ] At least 5 mappings (target 5–7)
- [ ] At least 2 of the mappings are `causal` or `process` (not all `structural`)
- [ ] At least one connected chain of 3 mappings exists (step1 → step2 → step3)
- [ ] `where_it_breaks` lists ≥3 specific weak spots
- [ ] `abstraction_level` is honest (don't claim `effect` for a parts-level mapping)
- [ ] `systematicity_score` calibrated: ≥0.7 only if there's at least one 3-step chain; ≥0.8 only if multiple chains interlock

If an analogy fails the checklist, **drop it** and try a different mechanism in the same domain, or move to another candidate domain.

## Two worked examples — good vs bad

### GOOD (deep structural mapping)

**Problem:** distribute fluid to variable-demand regions under pressure constraint
**Source domain:** cardiovascular physiology
**Mechanism:** mammalian baroreceptor-mediated blood pressure regulation

```
Mappings:
  causal     | ventricle contraction          ↔ central pump dispatch
  functional | arteriole smooth-muscle dilate ↔ local valve opens on demand signal
  causal     | baroreceptor feedback loop     ↔ pressure sensor adjusts pump rate
  structural | capillary bed parallel branch  ↔ distribution manifold splits flow
  constraint | viscosity rises at low flow    ↔ queue congestion at low throughput
  causal     | venous return sets preload     ↔ downstream backpressure limits dispatch

Where it breaks:
  - blood viscosity is non-Newtonian; engineered fluid usually isn't;
  - baroreceptor fatigue has no obvious mechanical analogue;
  - capillaries are autoregulated by local CO2 — what's the engineered analogue of a metabolic byproduct?

Systematicity: 0.82 (two connected causal chains: dispatch→pressure→sensor→rate; flow→preload→next-dispatch)
Abstraction level: effect (pressure-driven feedback loop is a thermodynamic principle)
```

Why it's good: 6 mappings, 3 causal, two chains, predicts non-obvious failure (non-Newtonian viscosity).

### BAD (surface-level)

**Problem:** distribute fluid to variable-demand regions
**Source domain:** computer networks
**Mechanism:** "the internet"

```
Mappings:
  structural | network nodes ↔ distribution points
  structural | network links ↔ pipes
Systematicity: 0.7 (claimed)
```

Why it's bad: 2 mappings, both structural, no causal chain, the "mechanism" is the entire field. This is "both have networks" — banned. Score 0.2 if it survives at all.

## On the "where it breaks" requirement

Every analogy has weak spots. An analogy with no documented failure modes is either (a) trivially true, or (b) you haven't thought about it. Both kill the value of the output.

The Synthesize stage uses `where_it_breaks` as inputs — every numbered step in `concrete_approach` should address at least one failure mode. So shallow `where_it_breaks` produces shallow solutions downstream. Spend the time here.

Good weak spots are **specific and asymmetric**:
- "Termite mounds use thermochemical gradients; the engineered wall has no CO2 production analogue" (specific)
- "It might not work everywhere" (banned — generic)

Aim for the kind of weak spot an expert in the source domain would point out within 10 seconds.

## Further reading (real papers, cite if useful)

- Gentner, D. (1983). *Structure-Mapping: A Theoretical Framework for Analogy.* Cognitive Science, 7(2).
- Gentner, D. & Markman, A. (1997). *Structure mapping in analogy and similarity.* American Psychologist.
- Holyoak, K. & Thagard, P. (1989). *Analogical Mapping by Constraint Satisfaction.* Cognitive Science.
- Hofstadter, D. & Sander, E. (2013). *Surfaces and Essences.* (book — long-form on analogy as the core of cognition)
