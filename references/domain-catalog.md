# Domain catalog (42 domains)

A curated set of domains spanning diverse fields, used in **Stage 3 (Expand)** to suggest candidate domains for analogical transfer. Not exhaustive — you may go beyond this list. The catalog exists to break recency bias and remind you of fields you wouldn't otherwise consider.

## How to use

In Stage 3, after running the four abstraction lenses:

1. **Exclude** the home domain and any closely adjacent category.
2. Pick **6–8** candidates that span at least 3 different categories below.
3. **Required mix**: ≥2 biology, ≥1 arts/humanities, ≥1 earth/physical sciences. (See SKILL.md.)
4. For each candidate, write a one-line rationale that names a **specific mechanism** you have in mind — not "this field is relevant".

## Categories and domains

### Biology

| Domain | Keywords | Description |
|--------|----------|-------------|
| **immunology** | immune, antibody, antigen, defense, pathogen | Defense mechanisms, self/non-self recognition |
| **mycology** | fungus, mycelium, spore, decomposition, network | Fungi, underground networks, lifecycle |
| **neuroscience** | neuron, brain, synapse, plasticity, cognition | Nervous systems, learning, memory |
| **ecology** | ecosystem, population, niche, succession, food web | Organism–environment interactions |
| **evolutionary biology** | evolution, selection, adaptation, fitness, mutation | How species change over time |
| **marine biology** | ocean, coral, deep sea, bioluminescence, pressure | Ocean life, extreme-pressure adaptations |
| **entomology** | insect, colony, swarm, metamorphosis, pheromone | Insects, colony behaviors, swarms |
| **botany** | plant, photosynthesis, root, growth, pollination | Plants and their processes |
| **microbiology** | bacteria, microbe, biofilm, quorum, culture | Microscopic organisms, quorum sensing |

### Physics

| Domain | Keywords | Description |
|--------|----------|-------------|
| **fluid dynamics** | flow, turbulence, viscosity, pressure, stream | Fluid motion and behavior |
| **thermodynamics** | heat, entropy, energy, equilibrium, cycle | Heat, energy, work |
| **materials science** | material, alloy, composite, crystal, polymer | Material properties and design |
| **optics** | light, lens, refraction, diffraction, spectrum | Light behavior and applications |
| **acoustics** | sound, wave, resonance, vibration, frequency | Sound and mechanical waves |
| **quantum mechanics** | quantum, superposition, entanglement, wave function, uncertainty | Subatomic particle behavior |

### Engineering

| Domain | Keywords | Description |
|--------|----------|-------------|
| **civil engineering** | structure, bridge, foundation, load, construction | Infrastructure design |
| **aerospace engineering** | flight, aerodynamics, propulsion, orbit, payload | Aircraft and spacecraft |
| **chemical engineering** | reactor, process, separation, catalyst, yield | Chemical process design |
| **electrical engineering** | circuit, signal, amplifier, filter, impedance | Electrical systems |

### Social

| Domain | Keywords | Description |
|--------|----------|-------------|
| **urban planning** | city, zoning, transit, density, infrastructure | Design of urban spaces |
| **economics** | market, supply, demand, incentive, equilibrium | Resource allocation, exchange |
| **organizational behavior** | team, leadership, culture, motivation, hierarchy | How organizations function |
| **epidemiology** | spread, contagion, outbreak, vaccination, herd immunity | Disease spread and control |
| **political science** | governance, policy, power, democracy, institution | Political systems and power |

### Earth Sciences

| Domain | Keywords | Description |
|--------|----------|-------------|
| **geology** | rock, tectonic, erosion, sediment, mineral | Earth's structure and processes |
| **meteorology** | weather, atmosphere, pressure, front, precipitation | Weather, atmospheric phenomena |
| **oceanography** | current, tide, salinity, depth, circulation | Ocean systems and processes |
| **soil science** | soil, nutrient, decomposition, layer, fertility | Soil formation and properties |

### Applied

| Domain | Keywords | Description |
|--------|----------|-------------|
| **logistics** | supply chain, routing, warehouse, delivery, inventory | Goods flow and distribution |
| **architecture** | building, space, design, ventilation, load | Buildings and spaces |
| **agriculture** | crop, irrigation, soil, harvest, rotation | Farming science and practice |
| **medicine** | diagnosis, treatment, surgery, drug, therapy | Healing and healthcare |
| **culinary arts** | cooking, fermentation, emulsion, reduction, seasoning | Science of food preparation |
| **textile science** | fiber, weave, dyeing, tension, fabric | Fibers, yarns, fabrics |

### Information & Mathematical

| Domain | Keywords | Description |
|--------|----------|-------------|
| **information theory** | entropy, channel, encoding, compression, noise | Mathematical study of information |
| **graph theory** | network, node, edge, path, connectivity | Mathematical study of networks |
| **game theory** | strategy, payoff, equilibrium, cooperation, defection | Strategic interaction |
| **cryptography** | encryption, key, hash, cipher, protocol | Secure communication |
| **signal processing** | filter, transform, frequency, noise, spectrum | Analysis of signals |

### Arts & Humanities

| Domain | Keywords | Description |
|--------|----------|-------------|
| **music theory** | harmony, rhythm, melody, counterpoint, resonance | Musical structure |
| **linguistics** | language, grammar, syntax, semantics, morphology | Language structure |
| **choreography** | movement, sequence, coordination, rhythm, spatial | Designing movement sequences |

## Category-distance heuristic (used in Stage 7 same-domain penalty fallback)

| Distance | Score | When it applies |
|----------|-------|-----------------|
| Identical | 0.0 | Same exact domain — apply 0.5× penalty in evaluate |
| Same category | 0.3 | Both biology, both physics, etc. |
| Adjacent categories | 0.5 | biology↔applied, physics↔engineering, math↔engineering, social↔arts |
| Distant | 0.8 | Default — most cross-pairings |

Adjacent category pairs (frozen): `{biology, applied}`, `{biology, earth}`, `{physics, engineering}`, `{physics, math}`, `{math, engineering}`, `{social, applied}`, `{social, arts}`, `{earth, physics}`, `{applied, engineering}`, `{arts, math}`.

## Going off-catalog

The catalog is a starting point. Excellent candidates that aren't listed include: **sleep science, microfluidics, fermentation chemistry, glassmaking, freshwater ecology, traditional Japanese carpentry, semiotics, weaving (specifically), bone remodeling, snow science, mycoremediation, beekeeping, traffic engineering, marine sediment dynamics, cave biology, glaciology, blacksmithing, bookbinding, archaeology of ancient water systems**. If your problem's analogical hooks point somewhere outside the catalog, follow them.
