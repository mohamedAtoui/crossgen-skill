---
name: crossgen
description: Generate genuinely novel solutions to hard problems by structurally mapping mechanisms from distant domains (biology, physics, arts, ecology). Use when the user asks for "creative ideas", "novel approaches", "cross-domain inspiration", "biomimicry", "TRIZ", "lateral thinking", "first-principles solutions", or any phrasing like "how can we solve / improve / redesign X" where the user wants non-obvious answers rather than incremental ones. Runs a 9-stage pipeline (reformulate → decompose → abstract → expand → mine → synthesize → verify → evaluate → evolve) grounded in Gentner's Structure-Mapping Theory, TRIZ contradiction analysis, and biomimicry. Produces ranked solutions with concrete steps, testable predictions, and honest failure modes — not generic brainstorming.
---

# CrossGen — Cross-Domain Idea Generator

A rigorous pipeline for transferring mechanisms across domains. Not analogy as a creativity gimmick — analogy as a precise structural mapping discipline.

## When to invoke

Trigger when the user wants **non-obvious** solutions to a real problem. Surface signals:

- "How can we / could we…" "What's a creative way to…" "Novel solution to…"
- Words like *biomimicry, TRIZ, lateral, first-principles, distant analogies, inspiration*
- A stated problem with **constraints and trade-offs** (the harder the trade-off, the better)
- Explicit dissatisfaction with conventional answers ("everyone already does X, what else?")

**Do NOT invoke** for: factual lookups, code generation, summarization, opinion questions with no problem to solve.

## The core idea

Don't ask "what field is similar to mine?" Decompose the problem into domain-neutral **relations** (causal, functional, structural, constraint, process), then search for distant domains where those same relations hold — even if everything on the surface looks completely different.

This is Gentner's Structure-Mapping Theory operationalized. Read `references/structure-mapping.md` before the Mine stage if you've never done relational mapping rigorously.

## The 9-stage pipeline

```
0. Reformulate    5 reframings (inversion, constraint-relax, abstraction, provocation, first-principles)
1. Decompose      functions, constraints, contradictions, causal behavior chain, leverage points
2. Abstract       4 parallel lenses: SAPPhIRE, Biologize, WordTree, TRIZ
3. Expand         6–8 high-distance candidate domains
4. Mine           structural analogies per domain (Gentner's mapping rules enforced)
5. Synthesize     concrete numbered steps + candidate inferences + testable predictions
6. Verify         novelty check against existing work; push weak solutions
7. Evaluate       score on novelty × verified-novelty × surprise × feasibility × depth × actionability
8. Evolve         mutate / recombine / critique top ideas
```

**Run the full pipeline** when the user wants real research-quality output (default).
**Run a quick pass** (skip stages 6–8) only if the user explicitly asks for a fast brainstorm.

## How to execute (workflow)

For each user problem, follow this exactly. Show progress between stages — don't disappear for 5 minutes.

### Stage 0 — Reformulate

Generate exactly **5 reframings** of the problem, each from a different cognitive lens:

1. **Inversion** — flip the goal. "Instead of reducing X, what if X became beneficial?"
2. **Constraint relaxation** — remove the single most constraining assumption.
3. **Domain-agnostic abstraction** — strip ALL domain-specific language. Express as a pure conceptual challenge anyone could recognize.
4. **Provocation** (de Bono) — deliberately absurd or impossible reframing to break mental patterns.
5. **First-principles** — decompose to fundamental truths, rebuild the question from scratch.

Each must be a complete problem statement, not a twist. Score each reframing's divergence (0.3 = minor rewording, 0.6 = different angle, 0.9 = completely different problem space). Pick the **2 most divergent** to run alongside the original — you now have 3 parallel paths.

### Stage 1 — Decompose (run per path)

For each path, extract:

- `domain` — the home domain (excluded from candidates later)
- `elaborated_problem` — 2–3 sentence expansion
- `primary_function` — domain-neutral verb (e.g., "selectively retain under capacity constraint", not "implement LRU cache")
- `sub_functions`, `constraints`, `parameters`
- `contradictions` — **at least 3**, expressed in physical/engineering vocabulary (use TRIZ-style parameters: speed, capacity, accuracy, reliability, complexity, adaptability, productivity — not domain jargon)
- `key_verbs` — 3–5 action verbs
- `behavior_chain` — causal sequence: input → step 1 causes step 2 → … → achieves function
- `leverage_points` — 2–4 Meadows-level intervention points (constants | feedbacks | information_flows | rules | self_organization | goals | paradigms)
- `analogical_hooks` — 2–3 aspects most amenable to cross-domain metaphor

### Stage 2 — Abstract (4 lenses in parallel)

**SAPPhIRE** — push to the deepest scientific principle. "Caching" → "selective retention under resource constraint" → "thermodynamic free-energy minimization". Levels: effect (deepest) → phenomenon → action → parts. Aim for `effect`.

**Biologize** — generate ≥6 "How does nature…?" reframings + ≥3 inversions ("How does nature *benefit from* the constraint?"). Then cite ≥4 specific biological strategies with named organisms and mechanisms. Strategies must be **real**, not invented.

**WordTree** — for each key verb, produce 3–5 hypernyms (more general), 3–5 troponyms (more specific manner-of), 3–5 cross-domain bridge terms.

**TRIZ** — for each contradiction, map to TRIZ parameters and look up principles in `references/triz.md`. The matrix is deterministic — don't hallucinate principle numbers, look them up.

### Stage 3 — Expand

Surface **6–8 candidate domains** for analogical transfer. Use `references/domain-catalog.md` for inspiration and `references/universal-principles.md` to find cross-domain principles whose other-domain bindings suggest candidates.

Strict rules:
- **NEVER include the home domain** or closely adjacent fields
- ≥2 from biology/ecology (mycology, immunology, marine biology, entomology…)
- ≥1 from arts/humanities (music theory, choreography, linguistics…)
- ≥1 from earth/physical sciences
- Each domain must connect to a different aspect of the problem
- For each, cite which lens (SAPPhIRE / Biologize / WordTree / TRIZ / universal) surfaced it
- In the rationale, hint at the **specific mechanism** in mind — not just "this domain is relevant"

### Stage 4 — Mine (per candidate domain)

This is the most important stage. Read `references/structure-mapping.md` if you haven't internalized Gentner.

For each candidate domain, identify **one specific real mechanism** (named phenomenon, not vague concept), then produce a `StructuralAnalogy`:

- `mechanism` — the specific mechanism (e.g., "mammalian baroreceptor-mediated blood pressure regulation", not "cardiovascular system")
- `mappings` — **5–7 one-to-one** correspondences, each typed: `causal | functional | structural | constraint | process`. Map the **behavior chain step-by-step**, not just static parts. Aim for chains of relations, not isolated matches.
- `where_it_breaks` — **mandatory.** Describe ≥3 specific weak spots as a single string separated by semicolons. This is non-negotiable; honesty here is what separates rigorous analogy from inspiration porn.
- `abstraction_level` — effect | phenomenon | action | parts
- `systematicity_score` — 0.0–1.0, higher = more relational correspondences in connected chains

**Banned**: "Both involve networks." "Both have feedback." Map HOW the network functions, HOW the feedback closes the loop, step-by-step.

If a domain produces fewer than 5 mappings or no causal chain, drop it and try another from the candidate list.

### Stage 5 — Synthesize (per analogy)

Convert each analogy into a concrete solution:

- `source_domain` + `source_mechanism`
- `concrete_approach` — **numbered steps** (Step 1, Step 2…) that are specific and actionable. Each step must explicitly address how it works around at least one of the weak spots from `where_it_breaks`.
- `candidate_inferences` — what the source predicts about the target that isn't obvious (Gentner's "candidate inference"). ≥2 per solution.
- `key_predictions` — **testable, falsifiable** predictions someone could measure. ≥2. These are the most valuable outputs of the entire pipeline.
- `transfer_strength` — strong | moderate | weak (honest assessment, "weak" is valid)
- `feasibility_notes` — practical barriers, materials, costs, what someone could do this week
- `research_pointers` — Google Scholar queries, key technical terms, seminal works (only cite works you're confident exist)

After all 3 paths run, you'll have many solutions. **Deduplicate** by (source_domain, source_mechanism) lowercased.

### Stage 6 — Verify novelty

For each solution, think hard: what existing approaches, methods, inventions, patents, or published ideas already solve this problem similarly? Consider academic literature, industry practice, prior cross-domain transfers.

Score `verified_novelty_score`:
- 0.0–0.2: this exact approach is well-known
- 0.2–0.4: close variants exist, minor twist
- 0.4–0.6: related approaches exist but this combines elements in a new way
- 0.6–0.8: genuinely novel combination or transfer, not previously attempted
- 0.8–1.0: no known similar approach exists

For any solution scoring <0.5, **push it**: rewrite to maximize novelty while preserving the structural mapping and the unique aspect of the source mechanism. Keep it practical.

### Stage 7 — Evaluate & rank

Score each solution on six dimensions using `references/scoring-rubric.md` for calibration. Be calibrated and honest — most scores should be in the 0.4–0.7 range. Reserve >0.8 for genuinely exceptional output.

Combined score:
```
score = 0.15·novelty + 0.25·verified_novelty + 0.15·surprise
      + 0.20·feasibility + 0.15·structural_depth + 0.10·actionability
```

Apply a **same-domain penalty** (multiply by 0.5) if `source_domain == home_domain` — any leak through the Expand filter must be punished.

Rank descending by combined score.

### Stage 8 — Evolve top ideas

Take the top 3–5 solutions and produce variants by applying ONE of:

- **mechanism_swap** — keep the source domain, different mechanism from it
- **scale_shift** — same mechanism at radically different scale (micro↔macro)
- **constraint_flip** — turn the solution's biggest limitation into a feature
- **domain_blend** — blend in a second, unrelated domain's mechanism

Optionally **recombine** two strong solutions into a hybrid. Optionally **critique-and-strengthen**: list 3+ fatal flaws, then rewrite addressing each while preserving novelty.

Re-rank the merged list (originals + evolved).

## Output

Format the final report following `references/output-template.md`. Always include:

1. The problem (original + 2 selected reframings with reasoning)
2. Pipeline statistics (paths, total solutions, after-dedup, avg novelty, top score)
3. **Top 10 solutions** with mechanism, score table (novelty | surprise | verified | feasibility | depth | score), concrete approach (numbered), key predictions
4. Honest acknowledgment of where each top solution breaks
5. Research pointers for the top 3

## Reference files (load on demand)

| File | When to load |
|------|-------------|
| `references/structure-mapping.md` | Before Stage 4 (Mine) if rusty on Gentner's rules |
| `references/universal-principles.md` | Stage 2 (TRIZ-lens fallback) and Stage 3 (domain expansion) |
| `references/domain-catalog.md` | Stage 3 (Expand) for candidate inspiration |
| `references/triz.md` | Stage 2 (TRIZ lens) — contradiction matrix and 40 principles |
| `references/scoring-rubric.md` | Stage 7 (Evaluate) for calibration examples |
| `references/output-template.md` | End — final formatting |
| `examples/extreme-heat-cities.md` | Anytime — see the quality bar |

## Non-negotiables (these are what make the output good)

- **Map relations, not surface features.** Banned: "both have networks." Required: map how the network functions step-by-step.
- **"Where it breaks" is mandatory** for every analogy. ≥3 weak spots. No exceptions.
- **Numbered concrete steps** in every solution. No "use X principles to inspire Y" hand-waving.
- **Testable predictions** in every solution. If you can't write a falsifiable prediction, the analogy isn't deep enough — go back to Stage 4.
- **Never use the home domain** as a candidate. The same-domain penalty exists for a reason; respect the filter upstream.
- **TRIZ is deterministic.** Look up principles in the matrix; do not invent principle numbers.
- **Cite real biology.** Named organisms, named mechanisms. No "some birds do X" — say which birds and what mechanism.
- **Calibrate honestly.** Most novelty scores belong in 0.4–0.7. If everything scores >0.8, you're not being a critic.

## A note on speed

The full pipeline is large. For a single non-trivial problem expect 15–30 minutes of focused work and a 4–8K word output. If the user wants something shorter, run a single path (skip Stage 0's parallel reframings) and skip Stage 8 (Evolve) — but never skip Stage 4's structural rigor or Stage 6's novelty check. That's where the value lives.
