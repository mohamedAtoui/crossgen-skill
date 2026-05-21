# Stage prompts (verbatim templates)

These are the exact prompt templates used by the original CrossGen pipeline. When you (Claude) are running this skill, you don't need to literally use these as separate API calls — they're your own thinking script. But the framing, vocabulary, and JSON shapes have been tuned for output quality. Follow them.

If the user requests an OpenAI-compatible or programmatic interface to the original pipeline, the underlying templates are these.

---

## Stage 0 — Reformulate

> You are a creative problem reformulation expert trained in de Bono's lateral thinking, first-principles reasoning, and the Idea-Catalyst methodology.
>
> Given a problem statement, generate **5 reframings** using DIFFERENT cognitive techniques. Each reframing should open up an entirely different solution space.
>
> Apply these 5 techniques (one reframing per technique):
>
> 1. **Inversion** — Flip the problem: "Instead of reducing X, what if X became beneficial?"
> 2. **Constraint relaxation** — Remove the most constraining assumption: "What if [key constraint] didn't exist?"
> 3. **Domain-agnostic abstraction** — Strip ALL domain-specific language. Express as a pure conceptual challenge anyone could recognize.
> 4. **Provocative operation** (de Bono) — Deliberately absurd or impossible reframing to break mental patterns.
> 5. **First-principles** — Decompose to the fundamental truths underlying the problem, then rebuild the question from scratch.
>
> For each, output `technique`, `reframed_problem` (a complete problem statement, not just a twist), `reasoning` (why this opens new solution spaces), and `divergence_from_original` (0.3 = minor rewording, 0.6 = different angle, 0.9 = completely different problem space).
>
> Then select the **2 most divergent** reframings that are (a) most divergent from each other and from the original, (b) most likely to lead to genuinely different solution spaces, and (c) still tractable.

---

## Stage 1 — Decompose

> You are a systems analyst specializing in functional decomposition.
>
> First, ELABORATE the terse problem statement into a rich 2–3 sentence description. Then trace the causal chain: input → step 1 causes step 2 → … → achieves function.
>
> Extract: `original_problem`, `elaborated_problem`, `domain`, `operating_context`, `current_state`, `desired_outcome`, `primary_function` (stated in domain-neutral terms — e.g., "selectively retain under capacity constraint" not "implement LRU cache"), `sub_functions`, `constraints`, `parameters`, `contradictions` (≥3, using physical/engineering vocabulary — speed, capacity, accuracy, reliability, complexity, energy, overhead, adaptability, productivity), `key_verbs` (3–5 action verbs), `analogical_hooks` (2–3 aspects amenable to cross-domain metaphor), `behavior_chain` (causal sequence where each step causes the next), `leverage_points` (2–4 Meadows-level intervention points: constants | feedbacks | information_flows | rules | self_organization | goals | paradigms).

---

## Stage 2a — SAPPhIRE lens

> You are a scientist applying the SAPPhIRE abstraction framework. SAPPhIRE hierarchy (most abstract → most concrete):
>
> - **Effect** — the underlying scientific principle (thermodynamic equilibrium, natural selection, wave interference)
> - **Phenomenon** — the observable behavior that results from the effect
> - **Action** — the action/process that causes the phenomenon
> - **Parts** — the physical or logical components
>
> Identify the deepest scientific principle at play. "Caching" → "selective retention under resource constraint" → "thermodynamic free-energy minimization". The Effect should be expressible in domain-neutral scientific language. Consider principles from thermodynamics, information theory, evolutionary biology, control theory, statistical mechanics.

## Stage 2b — Biologize lens

> You are a biomimicry expert. "Biologize" the technical problem — reframe it as questions nature has already solved.
>
> Generate **≥6 "How does nature…?" questions** with different framings (vary the level of abstraction). Generate **≥3 inversions** ("How does nature AVOID X?", "How does nature BENEFIT FROM the constraint itself?", "How does nature TURN the limitation INTO an advantage?"). Then cite **≥4 specific biological strategies** with named organisms and named mechanisms (REAL, not invented).
>
> Think beyond obvious parallels — organisms in extreme environments, symbiotic relationships, developmental biology.

## Stage 2c — WordTree lens

> You are a computational linguist specializing in semantic relationships.
>
> For each key verb, expand it into a WordTree of hypernyms (more general) and troponyms (more specific manner-of), plus cross-domain terms that bridge to other fields.
>
> Example for "filter": hypernyms = [select, discriminate, sort]; troponyms = [sieve, screen, distill, curate]; cross-domain = [fluid dynamics, signal processing, social curation, biological membrane].
>
> Aim for 3–5 of each per verb. Cross-domain terms should explicitly suggest fields OUTSIDE the home domain.

## Stage 2d — TRIZ lens

> Map each contradiction from Stage 1 to TRIZ engineering parameters. Look up principles in the contradiction matrix (see `references/triz.md` — deterministic, do not invent numbers). For each mapped contradiction, list the principles with their numbers and one-sentence relevance.
>
> If a contradiction doesn't map cleanly, select 3–5 principles by judgment and explain why each helps resolve it.

---

## Stage 3 — Expand

> You are a cross-domain innovation researcher.
>
> Identify **6–8 candidate domains** for analogical transfer. Use the SAPPhIRE Effect, nature questions, cross-domain WordTree terms, TRIZ principles, and matched universal principles as input.
>
> For each candidate: `domain`, `rationale` (which lens connected it AND the specific mechanism in mind), `source_lens` (sapphire | biologize | wordtree | triz | universal_principles), `distance_from_home` (low | medium | high).
>
> CRITICAL RULES:
> - **NEVER include the home domain** or closely adjacent fields
> - Prefer HIGH distance domains
> - ≥2 from biology/ecology
> - ≥1 from arts/humanities
> - ≥1 from earth/physical sciences
> - Each domain connects to a DIFFERENT aspect of the problem

---

## Stage 4 — Mine (per source domain)

> You are an analogical reasoning expert trained in Gentner's Structure-Mapping Theory.
>
> Find a SPECIFIC mechanism in the source domain that maps structurally to the target. Map behavior steps, not static functions — trace HOW the mechanism operates step-by-step.
>
> Output: `source_domain`, `mechanism` (a real, specific phenomenon — not vague concept), `mappings` (5–7 one-to-one `{source_element, target_element, relation_type: causal|functional|structural|constraint|process}`), `where_it_breaks` (≥3 weak spots as a single string separated by semicolons), `abstraction_level` (effect | phenomenon | action | parts), `systematicity_score` (0.0–1.0).
>
> CRITICAL RULES (Gentner):
> 1. Map RELATIONS, not surface features. "Both involve networks" is BANNED.
> 2. Prefer systematic mappings — connected chains of relations.
> 3. Each mapping is a one-to-one correspondence between specific elements.
> 4. The mechanism must be REAL and SPECIFIC.
> 5. `where_it_breaks` is REQUIRED — ≥3 specific weak spots.
> 6. Aim for 5–7 mappings minimum.
> 7. Use analogical hooks and the SAPPhIRE Effect to find deeper parallels.
> 8. Map the target behavior chain step-by-step to corresponding source-domain steps.

### Retrieval phase (MAC/FAC-inspired, optional)

> Quickly identify 3–5 candidate mechanisms in the source domain that could map structurally to the target. Provide a one-sentence rationale per candidate and a `relevance_score` (0.0–1.0). Pick the highest-scoring candidate for the full Mine pass above.

---

## Stage 5 — Synthesize (per analogy)

> You are an innovation engineer specializing in cross-domain technology transfer.
>
> Translate the analogy into a concrete solution. Output:
>
> - `source_domain`, `source_mechanism`
> - `concrete_approach` — HOW to implement, as numbered steps (Step 1, Step 2…). Each step must explicitly address at least one weak spot from `where_it_breaks`.
> - `candidate_inferences` — non-obvious predictions from the source about the target (Gentner). ≥2.
> - `key_predictions` — TESTABLE, FALSIFIABLE predictions someone could measure. ≥2. **Most valuable output of the pipeline.**
> - `transfer_strength` — strong | moderate | weak (honest; weak is valid)
> - `feasibility_notes` — practical barriers, materials, costs, what someone could do this week
> - `research_pointers` — `{academic_searches: [Scholar queries], key_terms: [technical terms], seminal_works: [only papers you're confident exist]}`

---

## Stage 6 — Verify novelty

> You are a novelty verification expert. Assess whether each solution is genuinely new.
>
> For each: think hard about what existing approaches, methods, inventions, patents, or published ideas already solve this problem similarly. Consider academic literature, industry practice, prior cross-domain transfers, common approaches in the source domain already applied to the target.
>
> Output per solution: `similar_existing` (descriptions of known approaches), `novelty_delta` (what SPECIFICALLY is new), `verified_novelty_score` (0.0–1.0).
>
> Calibration:
> - 0.0–0.2: this exact approach is well-known and widely used
> - 0.2–0.4: close variants exist, minor twist
> - 0.4–0.6: related approaches exist but new combination
> - 0.6–0.8: genuinely novel, not previously attempted
> - 0.8–1.0: no known similar approach

### Push phase (for solutions scoring <0.5)

> Modify each weak solution to MAXIMIZE genuine novelty while: (1) preserving the structural mapping from its source domain, (2) focusing on the most unique aspect of the source mechanism, (3) keeping it practical and actionable.

---

## Stage 7 — Evaluate

> You are a cross-domain innovation evaluator. Score each solution on six dimensions. Be calibrated and honest.
>
> Dimensions (0.0–1.0): `novelty`, `feasibility`, `structural_depth`, `actionability`, `surprise`, and `verified_novelty` (carried over from Stage 6).
>
> Calibration examples:
> - Novelty 0.75: "Apply slime-mold network optimization to Tokyo rail — distant, validated by Tero et al."
> - Novelty 0.25: "Use a database index to speed up search — same field, obvious technique."
> - Structural depth 0.8: "6 causal mappings forming two feedback loops, predicts non-obvious failure mode."
> - Structural depth 0.2: "2 surface similarities: both have nodes and edges."
> - Surprise 0.85: "Completely overturns the assumption that X must be minimized."
> - Surprise 0.20: "Confirms what practitioners already suspect."
>
> Combined: `0.15·novelty + 0.25·verified_novelty + 0.15·surprise + 0.20·feasibility + 0.15·structural_depth + 0.10·actionability`
>
> Apply **same-domain penalty** (×0.5) if `source_domain == home_domain` (case-insensitive).

See `references/scoring-rubric.md` for the full per-dimension calibration table.

---

## Stage 8 — Evolve

### Mutate

> Take a solution and MUTATE it — change ONE key aspect. Choose the most promising of:
> - **mechanism_swap** — keep the source domain but use a DIFFERENT mechanism from it
> - **scale_shift** — same mechanism at radically different scale (micro→macro or vice versa)
> - **constraint_flip** — take the biggest limitation, turn it into a feature
> - **domain_blend** — blend in a mechanism from a second, unrelated domain
>
> Output the mutation type and the mutated solution (same shape as Stage 5).

### Recombine

> Take TWO solutions and merge them. Combine the structural mapping from Solution A with the mechanism from Solution B (or vice versa). Find a creative synthesis, not an average.

### Critique-and-strengthen

> 1. CRITIQUE: List 3+ FATAL flaws — specific, harsh, actionable. At least one must address feasibility (cost, timeline, practical barrier).
> 2. STRENGTHEN: Produce an improved version addressing every flaw, preserving the core insight. Concrete next steps someone could take THIS WEEK in `feasibility_notes`.

---

## Optional — Research enrichment (deep mode)

> Search for academic papers about the source mechanism, existing cross-domain transfers to the target, and quantitative data from the source that could calibrate the transfer.
>
> Only cite papers/data you actually verify — do not fabricate references. Quantitative data should be specific numbers, rates, or measurements.

If you have web search available (WebSearch), use it for this stage. Otherwise, skip and note in output: "Research enrichment skipped — no web access."
