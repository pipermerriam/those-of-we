# Component Deep-Dive: Combat & Evasion

## The Core Problem
Single-cell player is weak. Direct confrontation loses. Survival requires:
1. **Avoidance** — detecting and fleeing threats
2. **Ambush** — striking when conditions favor you
3. **Environment** — using terrain/physics against enemies
4. **Specialization** — terrain-specific adaptations that trade mobility for 

## Threat Types

### Viruses
- **Threat:** Injects code that hijacks your programming, converting you to virus factory
- **Detection:** Mechanoreceptor (physical contact) or specialized Antigen Receptor
- **Counters:** 
  - Lysosome sacs (digest on contact before injection)
  - Rapid membrane shedding (sacrifice section to escape)
  - Temperature spike (viruses have narrow thermal tolerance)

### Predatory Bacteria
- **Threat:** Larger, faster, engulf you via phagocytosis
- **Detection:** Size estimation via shadow/light occlusion, chemical trail detection
- **Counters:**
  - Toxin secretion (consumes resources, zone denial)
  - Jet escape (contractile ring + fluid expulsion = burst speed, expensive)
  - Colony safety (aggregating makes engulfment harder)

### Environmental Hazards
- **Osmotic shock** — sudden salinity changes rupture membrane
- **UV radiation** — damages components, requires repair or shielding
- **pH extremes** — denatures proteins, stops reactions
- **Anoxic zones** — no oxygen/fuel, must store ATP or flee

## Combat Mechanics (Asymmetric)

### Acidic Cloud
- Component: Acid Vesicle + Contractile + Trigger
- Releases low-pH burst consuming ATP and Lipid
- Damages unprotected membrane on contact
- Friendly fire risk — your own membrane vulnerable too

### Spike Formation
- Component: Cytoskeletal Rigidifier + Ionic Accumulator
- Projects mineralized spike from membrane
- Pierces target membrane → causes leak → they bleed resources
- Static defense — limits mobility while deployed

### Suffocation Strategy
- Component: Rapid Growth + Membrane Sealing
- Surround threat, fuse membrane, seal them in
- Requires coordinated colony execution
- Target suffocates/starves trapped inside your envelope

### Resource Denial
- Toxin field makes area unlivable
- Out-compete for fuel sources
- Force migration into worse terrain

## Evasion Primitives

### Burst Propulsion
- Consume ATP rapidly → flagellum overdrive
- Leaves obvious chemical wake (tradeoff: speed vs stealth)
- Risk: overshoot food sources, enter new danger zones

### Streamlining
- Shed non-essential components to reduce drag
- Faster escape but temporarily weakened
- Must rebuild from reserves after

### Camouflage
- Match chemical signature of background
- Confuses chemoreceptor-based pursuit
- Ineffective against mechanoreceptors or vision

### Quorum Cloaking
- Chemical signals synchronized with colony
- Predator receives conflicting gradient vectors
- Confused pursuit → escape window

## The "Weak But Clever" Fantasy

Player should feel like they're solving puzzles, not grinding stats:
- Cannot out-tank viruses → must out-maneuver
- Cannot out-swarm predators → must out-think
- Cannot out-last environment → must out-plan

Victory conditions are environmental setup, not stat accumulation.
