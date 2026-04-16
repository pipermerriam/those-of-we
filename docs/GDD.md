# Game Design Document - Those of We

**A factory automation game with biological progression**

---

## Concept Overview

"Those of We" (working title, referencing Adrian Tchaikovsky's Children of Time series) is a factory automation game where you play as a single cell bacteria "going on an adventure."

---

## Core Gameplay Arc

### Stage 1: Single Cell Survival
- Start as a single bacterium struggling to survive
- Fight viruses and other microscopic threats
- Combat the few things you are stronger than to gain resources
- Reproduce to grow your presence
- **Core tension:** You are weaker than almost everything; direct combat doesn't scale

### Stage 2: Infection & Control
- Develop the ability to infect other beings on the planet
- Control hosts from the inside
- Progress through increasingly complex organisms:
  - Single cells → Multi-cellular organisms → Small creatures → Large creatures
  - Eventually all living matter becomes under your control

### Stage 3: Planetary Automation
- Once all biological matter is controlled, transition to planetary-scale automation
- Traditional factory/logistics gameplay at civilization scale

---

## Unique Mechanics

### Programmable Biological Systems

Rather than pre-fabricated buildings (conveyors, splitters, assemblers, miners), players:
- Disassemble the world piece by piece
- Assemble elementary components into useful tools/items
- Combine tools using **programmable logic** to create automation systems

### Visual Programming Language (v1 concept)
- Drag-and-drop visual scripting
- Components snap together into functional programs
- Constraints:
  - Maximum "space" available within a cell for components
  - Maximum total energy usage per cell
  - These limitations force clever, compact solutions

---

## Unresolved Questions

### Programming Metaphor
- Visual node-based scripting (current lean)
- Text-based DSL
- Biological metaphor (DNA/protein folding as programs)
- Hybrid approaches

### Scope Transitions
- How to handle time/scale jumps (bacteria → wolf → continent)
- Multiple concurrent simulations at different scales?
- Time compression?
- Player becomes the substrate (infection network = factory)?

### Disassembly Mechanics
- Reassembly-style: break down biomass into components
- Tools are also programmable agents
- Cross-scale reusability (e.g., flagellum repurposed as manipulator arm)

### Narrative Framing
- 2D or 3D?
- Pure simulation or narrative-driven?
- Core fantasy progression: Powerless cunning → Infectious puppetmaster → ??? (distributed godhood? world-scale overseer?)

---

## Cell Component System (Draft)

### Energy & Metabolism
| Component | Function |
|-----------|----------|
| **Mitochondria** | Power generation — burns fuel to produce ATP |
| **ATP Battery** | Energy storage — short-term energy reservoir |
| **Lipid Reserve** | Long-term storage — condensed fuel for extended operations |
| **Heat Vent** | Dissipates waste heat from reactions |
| **Insulation** | Retains heat for temperature-dependent reactions |

### Structure & Storage
| Component | Function |
|-----------|----------|
| **Membrane Section** | Structural integrity, defines cell boundary |
| **Ionic Rigidifier** | Converts flexible membrane to rigid cell wall |
| **Vacuole** | Storage chamber for materials/products |
| **Cytoskeletal Filament** | Internal support, enables shape changes |
| **Contractile Ring** | Active motor for pinching, squeezing |

### Transport & Logistics
| Component | Function |
|-----------|----------|
| **Flagellum** | Propulsion (consumes ATP) |
| **Cilia** | Localized movement, can be arrayed for pumping |
| **Ion Channel** | Passive transport across membrane |
| **Active Pump** | ATP-powered transport against gradients |
| **Vesicle Trap** | Captures and internalizes external materials |
| **Contractile Vacuole** | Expels waste or unwanted materials |

### Sensing & Signaling
| Component | Function |
|-----------|----------|
| **Chemoreceptor** | Detects chemical gradients (seek/flee) |
| **Mechanoreceptor** | Detects physical contact/pressure |
| **Thermoreceptor** | Detects temperature |
| **Photoreceptor** | Detects light (simple on/off or intensity) |
| **Signal Emitter** | Releases chemical signals |
| **Signal Receiver** | Responds to chemical signals |

### Processing (Programmable Logic)
| Component | Function |
|-----------|----------|
| **Logic Gate** | AND/OR/NOT/xor (2 inputs, 1 output) |
| **Threshold Detector** | Outputs when input exceeds threshold |
| **Comparator** | Compares two inputs, signals relation |
| **Timer** | Delays signals by configurable duration |
| **Oscillator** | Generates periodic pulses |
| **Memory Bit** | Stores 1 bit state until reset |
| **Counter** | Increments on pulses, outputs at threshold |
| **Sequencer** | Cycles through outputs in order |

### Reproduction & Growth
| Component | Function |
|-----------|----------|
| **Nucleoid** | Stores replication instructions (code/blueprint) |
| **Ribosome Factory** | Assembles new components from resources |
| **Replication Fork** | Initiates cell division when conditions met |
| **Plasmid Exchange** | Trade/shares blueprints with other cells |

---

## Base Resources (Atomics)

Gathered from environment through absorption/consumption:

1. **Glucose** — primary fuel source, burns for ATP
2. **Amino Acids** — building blocks for proteins/components
3. **Lipids** — membrane/fuel storage construction
4. **Nucleotides** — information storage, replication
5. **Ions** (Na+, K+, Ca2+, Cl-) — signaling, transport, structure
6. **Trace Minerals** — catalysts for specialized reactions
7. **Heat** — energy byproduct, can be useful or dangerous
8. **Waste Compounds** — expel or reprocess

---

## Interaction Model: Consumption

**Phagocytosis Flow:**
1. Detect target (chemoreceptor → logic → signal)
2. Move toward (flagellum/cilia control)
3. Engulf (membrane flexibility + contractile ring)
4. Digest (internal chemistry breaks down to resources)
5. Sort (active pumps move resources to vacuoles)
6. Expel waste (contractile vacuole)

**Membrane Permeability Control:**
- Gate ion channels open/closed programmatically
- Active pumps can scavenge specific resources even against gradient
- Vesicle traps snap shut on contact, consuming whatever touched

---

## Programming: Assembly from Components

Components snap together with I/O sockets:
- Each component has defined inputs (triggers, conditions) and outputs (signals, actions)
- Connections pass signals (boolean or scalar values)
- Signals travel instantly through connected graphs
- Cycles allowed but must resolve (simulation step)

### Example Simple Programs

**Seek Food:**
```
Chemoreceptor(glucose) → Comparator(gradient direction) → Flagellum(direction control)
```

**Digest When Full:**
```
Vacuole(fill level) → Threshold(>80%) → Contractile Ring(engulf pulse)
```

**Pulse Propulsion:**
```
Oscillator(2Hz) → Flagellum(burst mode when ATP>threshold)
```

**Heat Management:**
```
Thermoreceptor → Comparator(>optimal) → Heat Vent(open)
```

### Constraint: Cytoplasm Space
- Visual programming grid within cell boundary
- Each component consumes grid squares
- Membrane sections define available area
- Larger cells = more programming space but harder to heat/feed/move

### Constraint: Energy Budget
- Each component has passive draw (maintenance) and active draw (operation)
- Total ATP consumption cannot exceed production rate for sustained operation
- Burst capacity available from storage but depletes
- Failed programs can cascade (out of ATP → pumps stop → resources trapped → more problems)

---

## Next Deep-Dive Targets

1. **Combat mechanics** — how does a weak bacterium "fight" viruses/rivals?
2. **Infection progression** — what does taking over a multicellular organism look like?
3. **Scale 2+ design** — how do colony-level programs work?
4. **Tech tree pacing** — what unlocks when, how does complexity ramp?

---

## Tchaikovsky Influence

- **Children of Time:** Spiders evolve civilization from biology
- **Those of We:** Automation emerging from hijacked biological processes?
- Is the planetary pivot a hard genre break or organic evolution?

---

*See also: `combat.md` for detailed combat mechanics*
