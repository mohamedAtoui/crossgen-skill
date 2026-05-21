# TRIZ — 40 Inventive Principles + Contradiction Matrix

TRIZ (Теория решения изобретательских задач — Theory of Inventive Problem Solving) is a body of analysis tools distilled from a study of ~3M patents. It treats invention as a systematic process: identify the contradiction, look up principles that have historically resolved it, adapt.

Used in **Stage 2d (TRIZ lens)** and feeds into **Stage 3 (Expand)**.

## How to use in this skill

1. From Stage 1, you have ≥3 `contradictions`, each with `improving` and `worsening` parameters expressed in physical/engineering vocabulary.
2. Map each contradiction to two TRIZ parameter numbers using the parameter table + keyword guide below.
3. Look up the (improving, worsening) pair in the **Contradiction Matrix** below. This returns a list of principle numbers.
4. Read those principles. For each, write a one-sentence relevance note for the problem.
5. Feed these principles into Stage 3 (Expand) as candidate-domain seeds. (Principle 31 "Porous materials" → consider sponges, biofilms, aerogels, bone, foam metals, etc.)

**Important:** TRIZ is deterministic. Do not invent principle numbers. Look them up.

If a contradiction doesn't appear in the matrix below (the matrix is a curated subset of the full 39×39), pick the 3–5 principles you judge most relevant by reading the full list. Don't fake a lookup.

---

## The 39 Engineering Parameters

| # | Parameter | Common keywords |
|---|-----------|------------------|
| 1 | Weight of moving object | weight, mass, heavy, light, moving |
| 2 | Weight of stationary object | weight, mass, stationary, static |
| 3 | Length of moving object | length, distance, moving |
| 4 | Length of stationary object | length, distance, stationary |
| 5 | Area of moving object | area, surface, footprint, moving |
| 6 | Area of stationary object | area, surface, footprint, stationary |
| 7 | Volume of moving object | volume, size, space, capacity, RAM, VRAM, buffer, cache size |
| 8 | Volume of stationary object | volume, storage, disk, footprint |
| 9 | Speed | speed, velocity, latency, throughput, rate, bandwidth, tokens/sec |
| 10 | Force / Intensity | force, intensity, power, pressure |
| 11 | Stress or pressure | stress, pressure, tension, load |
| 12 | Shape | shape, form, structure, geometry, topology |
| 13 | Stability of object's composition | stability, consistency, robustness, steady |
| 14 | Strength | strength, durability, resilience, hardness |
| 15 | Duration of action (moving object) | duration, lifetime |
| 16 | Duration of action (stationary object) | duration, lifetime |
| 17 | Temperature | temperature, heat, thermal, cooling |
| 18 | Illumination intensity | brightness, illumination |
| 19 | Energy use (moving) | energy, power consumption, resource use |
| 20 | Energy use (stationary) | energy, power consumption |
| 21 | Power | power, wattage, output, performance |
| 22 | Loss of energy | energy loss, waste, dissipation, overhead, wasted cycles |
| 23 | Loss of substance | substance loss, material loss, data loss |
| 24 | Loss of information | information loss, data loss, fidelity, accuracy degradation, approximation error |
| 25 | Loss of time | time loss, delay, latency, downtime, recomputation, wall time |
| 26 | Quantity of substance/matter | quantity, amount, count |
| 27 | Reliability | reliability, uptime, availability, fault tolerance, correctness |
| 28 | Measurement accuracy | accuracy, precision, measurement, resolution |
| 29 | Manufacturing precision | manufacturing precision, build quality, tolerance |
| 30 | Object-affected harmful factors | harmful factors, external harm, vulnerability |
| 31 | Object-generated harmful factors | harmful side effects, pollution, noise, interference |
| 32 | Ease of manufacture | manufacturability, ease of implementation |
| 33 | Ease of operation | usability, UX, convenience, ergonomics |
| 34 | Ease of repair | maintainability, serviceability, debuggability |
| 35 | Adaptability or versatility | adaptability, flexibility, configurability, extensibility |
| 36 | Device complexity | complexity, implementation complexity, intricacy |
| 37 | Difficulty of detecting and measuring | detectability, observability, monitorability |
| 38 | Extent of automation | automation, autonomy, self-regulation |
| 39 | Productivity | productivity, efficiency, throughput, FLOPS |

---

## The 40 Inventive Principles

Each entry: # — Name. Description. *Examples.*

1. **Segmentation.** Divide an object into independent parts; make it sectional; increase fragmentation. *Modular furniture, sectioned containers, multi-blade razors.*
2. **Taking out / Extraction.** Separate an interfering part or property; single out the only necessary part. *Noise-canceling headphones extract anti-noise; extract heat from a process.*
3. **Local quality.** Change structure from uniform to non-uniform; each part functions in conditions suitable for it. *Pencil with eraser; bifocal lenses; multi-zone climate control.*
4. **Asymmetry.** Change from symmetrical to asymmetrical. *Asymmetric tires for grip; ergonomic handles.*
5. **Merging / Consolidation.** Bring together identical or similar objects; assemble identical parts to perform parallel operations. *Multi-core processors, bundled cables, combine harvester.*
6. **Universality.** Make a part perform multiple functions; eliminate need for other parts. *Smartphone, Swiss army knife.*
7. **Nested doll / Nesting.** Place one object inside another. *Telescopic antenna, stacking chairs.*
8. **Anti-weight / Counterweight.** Compensate for weight by merging with objects that provide lift. *Helium balloons on heavy equipment; counterweights in elevators.*
9. **Preliminary anti-action.** Replace harmful action with anti-actions to control its harmful effects. *Pre-stress concrete; vaccination.*
10. **Preliminary action.** Perform required change fully or partially in advance. *Pre-pasted wallpaper, sterilized packaging, pre-compiled code.*
11. **Beforehand cushioning.** Prepare emergency means to compensate for low reliability. *Airbags, backup systems, checksums, circuit breakers.*
12. **Equipotentiality.** Change conditions so an object need not be raised or lowered. *Lock gates; pressure equalization valves.*
13. **The other way round / Inversion.** Invert the action; make movable parts fixed and vice versa; turn the object upside down. *Treadmill, rotary engine.*
14. **Spheroidality / Curvature.** Use curves instead of straight lines; spheres instead of cubes; spiral or rotary motion. *Arched bridges, ball bearings.*
15. **Dynamics.** Allow characteristics to change for optimum at each stage. *Adjustable steering wheel, dynamic pricing, adaptive algorithms.*
16. **Partial or excessive action.** If 100% is hard, use slightly less or slightly more. *Overfill and remove excess (painting).*
17. **Another dimension.** Move to multi-dimensional space; multi-layered assemblies; tilt or re-orient. *Spiral staircase, 3D printing, multi-story parking.*
18. **Mechanical vibration.** Cause an object to oscillate or vibrate; use resonance. *Ultrasonic cleaning, vibrating concrete pour.*
19. **Periodic action.** Replace continuous with periodic or pulsed action. *Pulsed laser, interval training, batch processing.*
20. **Continuity of useful action.** Eliminate all idle or intermittent actions. *Continuous casting, flywheel storage, pipeline processing.*
21. **Skipping / Rushing through.** Conduct a process at high speed to avoid harmful side effects. *High-speed cutting reduces heat damage; flash pasteurization.*
22. **Blessing in disguise.** Use harmful factors to achieve a positive effect; amplify the harmful factor until it becomes useful. *Use waste heat; controlled burns prevent wildfires.*
23. **Feedback.** Introduce feedback; if feedback exists, change its magnitude or influence. *Thermostat, PID controller, A/B testing.*
24. **Intermediary / Mediator.** Use a carrier article or process; merge one object temporarily with another. *Catalyst, adapter pattern, message broker.*
25. **Self-service.** Make an object serve itself; use waste resources, energy, or substances. *Self-cleaning oven, self-healing materials, garbage collection.*
26. **Copying.** Use simpler/cheaper copies instead of unavailable, expensive, or fragile objects. *Virtual prototypes, simulations, digital twins.*
27. **Cheap short-living objects.** Replace expensive object with multiple inexpensive ones, compromising on durability. *Disposable diapers, containerized microservices, A/B test variants.*
28. **Mechanics substitution.** Replace a mechanical means with sensory means (optical, acoustic, taste, smell). *Electric field instead of mechanical barrier; optical sorting.*
29. **Pneumatics and hydraulics.** Use gas/liquid parts instead of solid. *Inflatable structures, hydraulic press, air cushion.*
30. **Flexible shells and thin films.** Use flexible shells/thin films instead of 3D structures. *Bubble wrap, thin-film solar cells.*
31. **Porous materials.** Make an object porous or add porous elements; fill pores with useful substance. *Sponge filters, aerogel, porous bone implants.*
32. **Color changes.** Change color or transparency. *Photochromic lenses, thermochromic indicators, syntax highlighting.*
33. **Homogeneity.** Make objects interacting with the main object of the same material. *Ice container for ice cream, edible packaging.*
34. **Discarding and recovering.** Make parts that fulfilled their function go away; restore consumable parts during operation. *Rocket staging, biodegradable packaging, memory deallocation.*
35. **Parameter changes.** Change physical state, concentration, density, flexibility, temperature. *Freeze-drying, compressed gas storage, phase-change cooling.*
36. **Phase transitions.** Exploit phenomena occurring during phase transitions (volume change, heat loss/absorption). *Heat pipes, water expansion on freezing.*
37. **Thermal expansion.** Use thermal expansion/contraction; multiple materials with different coefficients. *Bimetallic thermostat, shrink-fit assembly.*
38. **Strong oxidants.** Replace common air with enriched air or oxygen; use ionized oxygen; use ozone. *Ozone water treatment, oxygen-enriched combustion.*
39. **Inert atmosphere.** Replace normal environment with inert one; add neutral or inert additives. *Nitrogen-packed food, noble gas welding, sandboxed execution.*
40. **Composite materials.** Change from uniform to composite materials. *Carbon fiber reinforced plastic, reinforced concrete, hybrid architectures.*

---

## Contradiction Matrix (curated subset)

Lookup format: `(improving_parameter#, worsening_parameter#) → [principle#, principle#, …]`

This matrix is a useful subset of Altshuller's full 39×39 matrix focusing on the most-used cells. If your contradiction isn't here, pick principles by judgment from the full list above.

| Improving \ Worsening | → | Principles |
|---|---|---|
| 9 Speed | 1 Weight (moving) | 2, 28, 13, 38 |
| 9 Speed | 2 Weight (stationary) | 13, 14, 8 |
| 9 Speed | 10 Force | 13, 28, 15, 19 |
| 9 Speed | 27 Reliability | 11, 35, 27, 28 |
| 9 Speed | 36 Complexity | 13, 35, 1 |
| 9 Speed | 39 Productivity | 28, 35, 13, 18 |
| 10 Force | 1 Weight (moving) | 8, 1, 37, 18 |
| 10 Force | 2 Weight (stationary) | 13, 28, 15, 12 |
| 10 Force | 9 Speed | 13, 28, 15, 19 |
| 10 Force | 13 Stability | 35, 10, 36 |
| 12 Shape | 32 Ease of manufacture | 14, 4, 15, 22 |
| 13 Stability | 35 Adaptability | 35, 15, 34, 18 |
| 14 Strength | 1 Weight (moving) | 1, 8, 40, 15 |
| 14 Strength | 2 Weight (stationary) | 40, 26, 27, 1 |
| 14 Strength | 32 Ease of manufacture | 1, 35, 11, 10 |
| 17 Temperature | 27 Reliability | 21, 36, 29, 31 |
| 21 Power | 22 Loss of energy | 19, 38, 7 |
| 21 Power | 27 Reliability | 2, 35, 22 |
| 22 Loss of energy | 9 Speed | 19, 38, 7 |
| 22 Loss of energy | 39 Productivity | 28, 10, 29, 35 |
| 24 Loss of information | 9 Speed | 10, 24, 35 |
| 24 Loss of information | 27 Reliability | 10, 28, 23 |
| 24 Loss of information | 36 Complexity | 24, 26, 28, 32 |
| 25 Loss of time | 27 Reliability | 10, 30, 4 |
| 25 Loss of time | 36 Complexity | 35, 28, 34, 4 |
| 25 Loss of time | 39 Productivity | 10, 37, 36, 5 |
| 27 Reliability | 9 Speed | 11, 35, 27, 28 |
| 27 Reliability | 25 Loss of time | 10, 30, 4 |
| 27 Reliability | 36 Complexity | 13, 35, 1 |
| 28 Measurement accuracy | 9 Speed | 28, 32, 13, 6 |
| 28 Measurement accuracy | 36 Complexity | 26, 24, 32, 28 |
| 30 Harmful (external) | 27 Reliability | 22, 21, 27, 39 |
| 31 Harmful (generated) | 27 Reliability | 19, 22, 31, 2 |
| 32 Ease of manufacture | 14 Strength | 1, 35, 11, 10 |
| 32 Ease of manufacture | 27 Reliability | 11, 13, 1 |
| 32 Ease of manufacture | 36 Complexity | 26, 24, 32, 28 |
| 33 Ease of operation | 27 Reliability | 25, 2, 13, 15 |
| 33 Ease of operation | 36 Complexity | 27, 22, 13, 24 |
| 35 Adaptability | 27 Reliability | 35, 1, 13, 11 |
| 35 Adaptability | 32 Ease of manufacture | 1, 15, 29, 4 |
| 35 Adaptability | 36 Complexity | 15, 29, 37, 28 |
| 36 Complexity | 27 Reliability | 26, 24, 32, 28 |
| 36 Complexity | 33 Ease of operation | 27, 22, 13, 24 |
| 36 Complexity | 35 Adaptability | 15, 29, 37, 28 |
| 38 Automation | 27 Reliability | 5, 12, 35, 26 |
| 38 Automation | 36 Complexity | 15, 24, 10 |
| 38 Automation | 39 Productivity | 5, 12, 35, 26 |
| 39 Productivity | 9 Speed | 28, 35, 13, 18 |
| 39 Productivity | 22 Loss of energy | 28, 10, 29, 35 |
| 39 Productivity | 27 Reliability | 35, 28, 2, 24 |
| 39 Productivity | 36 Complexity | 35, 28, 2, 24 |
| 5 Area (moving) | 1 Weight (moving) | 29, 30, 14, 5 |
| 6 Area (stationary) | 2 Weight (stationary) | 40, 29, 14, 5 |
| 7 Volume (moving) | 1 Weight (moving) | 2, 26, 29, 40 |
| 8 Volume (stationary) | 2 Weight (stationary) | 35, 10, 19, 14 |

## Example — using the matrix in Stage 2d

From Stage 1, suppose a problem has:

> Contradiction: improving "throughput" worsens "reliability"

1. Map "throughput" → parameter 9 (Speed) or parameter 39 (Productivity). Pick one — let's say 9.
2. Map "reliability" → parameter 27 (Reliability).
3. Look up `(9, 27)` → principles `[11, 35, 27, 28]`.
4. From the principles list: 11 = Beforehand cushioning; 35 = Parameter changes; 27 = Cheap short-living objects; 28 = Mechanics substitution.
5. Write one-sentence relevance for each:
   - **11 Beforehand cushioning** → introduce checksums, retries, or pre-allocated backup paths to absorb failure before it cascades.
   - **35 Parameter changes** → change the operating point (e.g. lower precision, different state) to gain reliability headroom.
   - **27 Cheap short-living objects** → replace expensive durable components with many cheap disposable ones (think containers, A/B variants).
   - **28 Mechanics substitution** → swap the mechanism for one in a different physical regime (optical, acoustic, electrical).
6. Feed those principles into Stage 3 (Expand) — Principle 27 suggests biological domains (cell turnover, R-selected species), Principle 28 suggests optics, acoustics, etc.
