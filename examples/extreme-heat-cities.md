# Example — Extreme heat cities

An abridged real CrossGen run. Use this as the quality bar: structural depth, named mechanisms, "where it breaks" addressed in concrete steps, testable predictions with quantitative thresholds.

> Full run produced 40 ranked solutions across 3 parallel reframings. This file shows the top 5 in compressed form. The complete report from the original Python pipeline is preserved in the source repo under `examples/extreme-heat-cities/SUMMARY.md` (~1500 lines, 40 solutions).

---

# CrossGen — Extreme heat cities

## Problem

> How can cities redesign urban infrastructure to remain functional when extreme heat events exceed 50°C for weeks at a time? Current infrastructure fails in cascade: asphalt softens and deforms, power grids collapse under air-conditioning load, outdoor labor becomes lethal, water demand spikes beyond supply, and concrete structures degrade. Traditional solutions like more AC just amplify the heat island effect and grid strain. We need fundamentally new approaches to urban heat resilience that break these feedback loops.

## Pipeline configuration

- **Mode:** full (9 stages)
- **Parallel paths:** 3 (original + 2 reframings)
- **Total solutions before dedup:** 32
- **After deduplication:** 32
- **Solutions verified novel (≥0.5):** 32
- **Solutions pushed:** 5
- **Evolved variants:** 8
- **Final ranked solutions:** 40
- **Average verified novelty:** 0.65
- **Top combined score:** 0.77

## Reformulations (2 selected from 5)

**Constraint Relaxation (divergence 0.75) — selected as Path 2**

> What if cities did not need to remain continuously inhabited and operational during extreme heat events — that is, what if the assumption of 24/7 fixed-location urban occupancy were removed? How would we design urban systems that allow populations to fluidly redistribute, hibernate, or temporally phase their presence so that peak heat load is met by near-zero human occupancy, and full urban function resumes only when conditions permit?

*Why this opens a different space:* The hidden master constraint is that cities must be simultaneously fully occupied AND fully functional during the crisis. Relaxing it reveals nomadic urban frameworks with climate-synced migration corridors, underground habitation layers activated only during heat events, distributed "cool refuges" networked across regions. Desert cultures, migratory species, and maritime industries have solved analogous problems.

**Provocation (divergence 0.95) — selected as Path 3**

> What if every building in the city were required by law to be hotter inside than outside during a heat event — forcing architects, engineers, and residents to design entirely new survival strategies premised on the impossibility of cooling — and in doing so, accidentally discover that biological, behavioral, and material adaptations exist that make thermal comfort achievable at 55°C without any energy expenditure at all?

*Why this opens a different space:* Demolishes the unexamined axiom that human comfort requires a cooler interior. Forces inquiry into what creatures, cultures, and materials already function at these temperatures without refrigeration: Hadza sleep outdoors at 45°C; termite mounds maintain 30°C inside 50°C environments through passive airflow geometry; Bedouin layered wool creates a microclimate cooler than the surrounding air.

> *Not selected: Inversion (0.82), Abstraction (0.88), First-principles (0.91) — strong but less divergent than the two chosen.*

## Problem decomposition (primary path)

- **Home domain:** urban planning / civil engineering
- **Primary function:** maintain habitable conditions under sustained extreme thermal forcing while bounded by energy and water supply
- **Key contradictions:**
  1. Reliability ↔ Energy use: more cooling = more grid load = more cascade risk
  2. Adaptability ↔ Complexity: dynamic response requires sensors/controls that fail under heat
  3. Productivity ↔ Harmful side effects: AC throughput vs. waste-heat amplification of heat island
- **Behavior chain:** ambient heat rises → AC compressor load rises → grid frequency drops → cascading failures → waste-heat amplifies heat island → ambient rises further (positive feedback loop)
- **Leverage points:**
  - Waste-heat re-injection rules (rules) — change which heat goes where
  - Real-time grid+thermal coupled telemetry (information_flows) — derivative trigger fires earlier
  - The assumption "all buildings cool continuously" (paradigms) — biggest lever

## Abstractions (compressed)

| Lens | Output |
|------|--------|
| SAPPhIRE | **Effect:** dissipative-structure stability under sustained driving force. **Phenomenon:** positive feedback loop with delayed nonlinear constraint |
| Biologize | How does nature thermoregulate at 50°C without active cooling? (termite mounds, camel nasal heat exchange, desert rodent burrows, plant transpiration cycling) |
| WordTree | "cool" → buffer / damp / lag / phase-shift / dissipate / radiate (cross-domain: signal processing, materials, ecology) |
| TRIZ | (27 Reliability vs 9 Speed) → 11 Beforehand cushioning, 35 Parameter changes, 27 Cheap short-living objects, 28 Mechanics substitution |

## Candidate domains explored (8)

| Domain | Distance | Lens | Rationale |
|--------|----------|------|-----------|
| Entomology (termites) | high | biologize | Macrotermes colonies regulate mound interior via passive thermal-stack ventilation |
| Permafrost geomorphology | high | universal | Stratified medium with calibrated thermal inertia, Stefan-controlled phase boundary |
| Immunology | high | universal | Treg-mediated counter-cytokine suppression as gain-dampening meta-feedback |
| Distributed systems (cache stampede) | high | wordtree | Thundering herd suppression via exponential backoff with jitter |
| Mycorrhizal networks | high | biologize | Decentralized resource transfer along gradient (carbon, phosphorus) |
| Marine bioluminescence | high | biologize | Quorum-sensed light only at threshold density (low-energy on-demand response) |
| Music theory (counterpoint) | high | wordtree | Voice independence under harmonic constraint (analog to building-level autonomy under grid constraint) |
| Materials science (shape-memory alloys) | medium | triz/35 | Thermal-driven mechanical actuation without electronic control |

---

# Top 5 solutions

## #1 — Termite mound architecture + thermomechanical passive actuation (SMA) [Evolved] (Score: 0.77)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.82 | 0.79 | 0.82 | 0.61 | 0.88 | 0.71 | **0.77** |

**Mechanism:** The original solution's fatal flaw — electrical micro-pump dependency that fails during the grid brownouts it is trying to mitigate — is inverted: the temperature differential produced by the heat event itself becomes the sole motive force for fluid switching. Termites never use electricity; they exploit thermochemical gradients that are strongest precisely when ventilation is most urgent. The mutated wall panel is driven by the thermal stress it is designed to resist. Nitinol shape-memory-alloy (SMA) micro-actuators embedded at every channel junction contract above ~35°C, mechanically dilating channels from ~0.8mm to ~3mm diameter, increasing effective thermal diffusivity α from 0.35 to ~1.8 mm²/s in discharge mode — with no pump, controller, or grid connection. The system is **anti-fragile**: the worse the heat event, the stronger the actuating force.

**Concrete approach:**

Step 1 — **Nitinol micro-valve channel network**: Fabricate 40–60mm geopolymer sandwich panels with printed micro-channel networks (channel diameter 1–3mm, spacing 8–15mm). Replace every branching junction with a Nitinol SMA wire loop trained to dilate at austenite transition T_a = 34–36°C (tunable via alloy composition). Below T_a, martensitic shape pinches the channel; above, austenite shape dilates it 4×. Working fluid: glycol-water with TiO₂ microspheres for radiative emissivity.

Step 2 — **Passive thermosiphon discharge loop**: Connect panel networks to roof-mounted radiative-cooling membranes (sky-facing emissivity ≥0.92 at 8–13µm). The dilated channels enable buoyancy-driven circulation; ΔT between hot wall (45°C) and cool roof (20°C night) drives ~0.19 m/s flow without pumps.

Step 3 — **Material-encoded jitter**: Across a precinct of 500 buildings, mandate Nitinol T_a tolerance of ±0.5°C (Gaussian σ ≈ 0.6°C). This produces a city-wide valve-opening time spread of ±18 minutes at a 2°C/hour ambient ramp — desynchronizing demand naturally via material heterogeneity. No firmware, no compliance layer, no defection risk.

Step 4 — **Failure-mode hardening**: Address the analogy's "no waste-heat analogue" weak spot by routing rejected heat to nocturnal radiative roof membranes (sky-coupled, not boundary-layer-coupled), preventing the heat-island amplification that killed prior approaches.

**Testable predictions:**
- A prototype panel with SMA micro-valves transitions from low-flow (α ≈ 0.35 mm²/s) to high-flow (α ≈ 1.6–1.9 mm²/s) within 8–12 minutes of fluid temperature crossing T_a = 35°C, measurable via fiber Bragg grating strain sensors.
- Thermosiphon velocity in a 1.8m vertical loop scales as v ∝ (ΔT)^0.5 with coefficient ~0.04 m/s·K^−0.5 — predicting v ≈ 0.19 m/s at ΔT = 20°C, sufficient for ≥60 W/m² discharge flux pumpless.
- A 1,000-panel production run with standard Nitinol (±0.5°C T_a) yields a Gaussian opening-time spread of ±18 min — quantitatively comparable to the original GPS-hash-driven jitter window.

**Where the analogy breaks:**
- Termites continuously rebuild — engineered panels can't self-repair after material fatigue (SMA hysteresis degrades after ~10⁴ cycles).
- Mound CO₂ is the convection driver in nature; the engineered panel has no metabolic byproduct analogue, so we substitute thermal-driven buoyancy.
- Real termite mounds are calibrated to specific local climates over generations; retrofitting cities requires upfront design effort with no centuries of iteration.

**Feasibility notes:** SMA wire ~$5/m; geopolymer panels existing technology; main risk is fatigue cycling beyond Nitinol's ~10⁴-cycle envelope. Pilot: 10 m² prototype on a single building roof, instrumented for one summer. Cost ~$30K including sensors.

**Research pointers:**
- Scholar: `"termite mound thermoregulation Turner"`
- Scholar: `"Nitinol shape memory thermal cycling fatigue"`
- Scholar: `"radiative cooling sky-facing 8-13 micron Raman"`
- Key terms: bioinspired ventilation, geopolymer thermal mass, passive nocturnal radiative cooling, Macrotermes Bellicosus

---

## #2 — Adaptive immune tolerance × distributed-systems stochastic backpressure [Evolved] (Score: 0.74)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.82 | 0.78 | 0.82 | 0.52 | 0.88 | 0.65 | **0.74** |

**Mechanism:** A hybrid: the four-channel parallel suppression topology of regulatory T-cell mediated immune tolerance (IL-10 / TGF-β / CTLA-4 / adenosine pathways) is driven not by static thresholds but by the derivative signals (dT/dt, d(loop-gain)/dt) of distributed-systems exponential backoff. The immune topology says **where and what** to suppress across parallel channels; the stochastic temporal control says **when, how fast, how deeply** — bounded by ethical P0 survivability floors that override all suppression. The city is treated as an immune system whose Treg activation is scheduled by exponential backoff rather than antigen density alone.

**Concrete approach:**

Step 1 — **Instrument loop-gain as primary trigger**, not temperature: deploy city-scale sensor fabric measuring G = [δ(cooling_demand)/δ(T_ambient)] × [δ(waste_heat_flux)/δ(cooling_demand)], estimated from AMI load data, condenser exhaust thermal cameras, and distributed WBGT stations. Trigger pre-emptively when dG/dt > threshold, 60–120 minutes before instability.

Step 2 — **Four parallel suppression channels** (mapping to Treg paracrine pathways):
- *Upstream attenuation*: cool-roof + high-albedo retrofits (≥0.7 SRI)
- *Local paracrine buffering*: PCM thermal storage at ≥60% building floor area
- *Costimulatory withdrawal*: dynamic time-of-use pricing for non-essential cooling loads
- *Proportional Treg scaling*: demand-response curtailment with derivative-triggered activation

Step 3 — **WBGT-bounded jitter exemptions**: P0 buildings (hospitals, eldercare, schools) bypass jitter entirely. Hard-coded survivability floor.

Step 4 — Address "fatigue" weak spot via rotating channel duty (no single channel carries full load for >4 hours).

**Testable predictions:**
- Cities with derivative-triggered (dG/dt) demand-response will experience measurably fewer cascade failures than threshold-triggered (G > G_max) cities at identical suppression depth, because derivative triggering intercepts instability 60–120 min earlier.
- Buildings receiving both nocturnal PER pre-cooling AND WBGT-bounded jitter exemptions will show zero heat-related-illness incidents during events where buildings receiving only pricing-signal DR (no survivability ceiling) show measurable morbidity.
- G-proportional jitter (window widening as G→1.0) produces Poisson-distributed demand that reduces peak-to-trough load ratio by >40% vs. step-function curtailment.

**Where the analogy breaks:**
- Treg suppression in the body is autonomous; demand-response curtailment requires governance compliance — brittle precisely when social cohesion is lowest.
- Cytokine pathways are biochemical and parallel; grid control is digital and serial — coordination latency is fundamentally different.
- Immune fatigue (Treg exhaustion in chronic inflammation) suggests demand-response programs lose effectiveness over multi-week events; need rotation policy not present in the source domain.

**Feasibility notes:** Sensor fabric uses existing AMI data + new thermal cameras ($2K each at neighborhood scale). Compliance is the biggest risk. Pilot in a utility territory with strong DR enrollment (CAISO, ERCOT) over 2 summers.

**Research pointers:**
- Scholar: `"regulatory T cell paracrine signaling tolerance"`
- Scholar: `"exponential backoff jitter thundering herd"`
- Scholar: `"derivative-triggered demand response heat event"`

---

## #3 — Cache invalidation × mycorrhizal network domain blend [Evolved] (Score: 0.71)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.82 | 0.79 | 0.82 | 0.41 | 0.87 | 0.62 | **0.71** |

**Mechanism:** The original solution's deepest constraint is that stochastic jitter must be imposed externally via firmware + governance + compliance — a sociotechnical layer brittle precisely when cohesion is lowest. The flip: engineer the built environment so the **physical thermal time constants of heterogeneous buildings ARE the jitter**. Each building's thermal mass, PCM phase-transition temperature, orientation, and albedo together constitute its natural "backoff clock". No firmware. No compliance. No defection risk. The mycorrhizal blend supplies a decentralized gradient-driven transfer layer that routes surplus stored cooling from thermally-rich nodes to thermally-poor ones — the thermal gradient IS the routing protocol.

**Concrete approach:**

Step 1 — **Abolish the firmware layer.** Replace software-enforced jitter with engineered material heterogeneity. Mandate via building code that each urban precinct (~500 buildings) spans at least three decades of thermal time constants: lightweight steel-frame τ ≈ 2h, mid-mass concrete τ ≈ 10h, high-mass earthen/PCM τ ≈ 48h.

Step 2 — **Brine-loop coolth-sharing network** (mycorrhizal analogue): inter-building underground brine loops at 8–14°C, with passive wax-motor valves opening when local demand exceeds local storage. Thermally-rich buildings (pre-cooled high-mass) export coolth to thermally-poor neighbors (lightweight construction). The 8°C gradient drives flow without pumps.

Step 3 — **Reciprocal credit mechanism**: tax credit per kWh-equivalent of measured coolth export. Aligns financial incentive with physical behavior — per-unit-exported, not per-event-participation.

Step 4 — Address "no central controller" failure mode with embedded stigmergic rules: each valve responds only to local pressure & temperature, no network connectivity needed.

**Testable predictions:**
- A district with engineered τ-heterogeneity (three thermal-mass tiers mandated by code) shows afternoon peak demand variance ≥40% lower than an adjacent district of homogeneous construction at identical climate exposure, measurable via AMI data without any DR activation.
- Brine-loop precincts with passive wax-motor actuators maintain loop supply temperature <14°C for ≥6 hours longer during a 45°C event than precincts relying on pump controllers drawing from the same grid.
- Reciprocal coolth-export credits produce pre-cooling behavior 2–3°C more aggressive than voluntary DR programs of equivalent monetary value, because credit is per-unit-exported.

**Where the analogy breaks:**
- Mycorrhizal networks evolved over millions of years to a specific symbiosis; brine loops are infrastructure with maintenance/leakage failure modes.
- Carbon/phosphorus transfer in fungi is unidirectional gradient-driven; coolth can reverse if a "rich" node depletes its storage faster than expected.
- Mandating material heterogeneity in retrofits is politically harder than in new builds.

**Feasibility notes:** Wax-motor valves used in existing radiator thermostats (~$15 each); brine-loop infrastructure costs ~$200/linear-meter; politically easier as a code amendment for new construction than retrofit. Pilot needs municipal partnership with strong climate plan.

**Research pointers:**
- Scholar: `"mycorrhizal common mycelial network carbon transfer Simard"`
- Scholar: `"cache stampede thundering herd exponential backoff"`
- Scholar: `"district cooling brine loop passive valve"`

---

## #4 — Immunological tolerance and anergy induction (Score: 0.72)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.82 | 0.78 | 0.58 | 0.61 | 0.91 | 0.65 | **0.72** |

**Mechanism:** Regulatory T-cell (Treg) CTLA-4 signaling and IL-10/TGF-β counter-cytokine suppression — a density-proportional, gain-dampening negative meta-feedback loop that restructures immune feedback topology rather than suppressing effector function outright, preventing cytokine storm while preserving pathogen clearance.

**Concrete approach (abridged):** Operate four parallel suppressive channels (upstream signal attenuation via cool roofs ≥0.7 SRI, local paracrine buffering via PCM, costimulatory withdrawal via dynamic pricing, proportional Treg scaling via DR curtailment) — partially redundant, none carrying full load.

**Testable predictions:**
- Urban air temperature increment from waste heat capped at <1.5°C above ambient during events that previously produced 2–5°C, measurable via condenser-exhaust thermal arrays (difference-in-differences across treatment/control neighborhoods).
- Neighborhoods with PCM thermal storage at ≥60% building floor area show grid demand spike ratio ≥35% lower than matched-morphology neighborhoods without PCM.
- Cool-roof deployment at ≥40% of rooftop area in a 1km² patch produces superlinear ambient cooling: 40% coverage yields >60% of the 100%-coverage cooling, due to aerodynamic mixing and view-factor geometry.

**Where the analogy breaks:** [3 weak spots — see solution #2 above which is the evolved variant addressing them]

---

## #5 — Permafrost & periglacial geomorphology [Path 2] (Score: 0.70)

| Novelty | Surprise | Verified Novelty | Feasibility | Depth | Actionability | **Score** |
|---------|----------|------------------|-------------|-------|---------------|-----------|
| 0.82 | 0.79 | 0.71 | 0.41 | 0.88 | 0.59 | **0.70** |

**Mechanism:** Active-layer freeze-thaw cycling above continuous permafrost — a Stefan thaw front propagates downward through depth-stratified material of increasing thermal inertia, reaches a phase-boundary discontinuity (the permafrost table), then refreezes bidirectionally. The deep substrate remains in metastable preservation encoding structural memory of prior cycles. Stress distributes across a tessellated polygon network rather than concentrating it; catastrophic thermokarst failure occurs only when thermal disturbance exceeds the reversible threshold of ice-rich permafrost.

**Concrete approach (abridged):** Engineer the city as a stratified medium with explicitly calibrated thermal inertia at each depth (asphalt → engineered subgrade → deep PCM layer at 1.5m → reference geothermal at 8m), governed by a Stefan-analog control law so extreme heat drives a predictable, bounded, reversible transition rather than crisis.

**Testable predictions:**
- A 4-layer stratified urban surface keeps deep-layer temperature swings within ±0.3°C during 50°C surface events that would shift unstratified asphalt by ±8°C.
- Tessellated thermal-expansion joints sized to permafrost polygon scale (~5m) eliminate buckling failures observed in continuous asphalt at >55°C.
- A PCM layer with 250 kJ/kg latent heat at 38°C, placed at 1.5m depth and 8cm thick, absorbs the equivalent of 6 hours of peak solar forcing per m² without thermal-front advancement past 2m.

**Where the analogy breaks:**
- Permafrost stability depends on millennia of climate; urban infrastructure has months.
- Polygon networks in tundra self-organize via freeze-thaw cycles; urban grids are imposed and rigid.
- Stefan-front analytical solutions assume homogeneous media; urban subsoil is full of pipes, cables, and historical fill.

---

## (Solutions 6–40 — listed compactly)

| Rank | Solution | Domain | Score |
|------|----------|--------|-------|
| 6 | Distributed systems cache × programmable thermal impedance hybrid [Evolved] | CS × entomology | 0.71 |
| 7 | Termite mound architecture (single-domain baseline) | entomology | 0.70 |
| 8 | Marine bioluminescence quorum sensing as on-demand cooling activation | marine biology | 0.69 |
| 9 | Sleep-cycle-coordinated metabolic load shedding | sleep science | 0.68 |
| 10 | Musical counterpoint (voice-independence under harmonic constraint) for building autonomy | music theory | 0.65 |
| 11–40 | [omitted for brevity in this example file] | | 0.40–0.64 |

---

# Diagnostics & honesty

- **Quality warnings:** None at quality gates. Two candidate domains (quantum mechanics, cryptography) returned <5 mappings and were dropped before synthesis.
- **Solutions pushed in Stage 6** (low initial novelty, rewritten): 5 solutions involving cool-roofs and PCM alone (all variants of well-known techniques) were rewritten to focus on the *combination* with passive actuation, raising their verified novelty from 0.35 to 0.65.
- **Same-domain penalty applied to:** Solution proposing "smart-city sensor mesh" was correctly flagged as urban planning (home domain) and downweighted to combined 0.21.

# Where this output is itself weak

- All top 5 implicitly assume centralized municipal capacity. In cities with weak governance, none implement cleanly — the "Constraint Relaxation" path's hibernation-friendly designs may matter more there.
- We did not deeply explore **traditional architecture** domains (Persian wind catchers, Yemeni mud towers, Hausa earthen architecture) which would have been higher-confidence biomimicry targets than termite mounds (humans already pulled it off).
- The "Provocation" reframing (heat as resource) under-produced — only 3 of 32 solutions came from Path 3. Either the reframing was too divergent, or we didn't mine enough domains under it. A re-run focusing exclusively on thermoelectric, absorption-cooling, and solar-thermal domains would likely add 5–10 strong candidates.
- Research pointers should be expanded to actual published papers via Google Scholar or Semantic Scholar before any prototype investment.
