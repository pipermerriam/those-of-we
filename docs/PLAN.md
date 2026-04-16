# Those of We - Implementation Plan

**Engine:** Godot 4.x  
**Genre:** Factory automation with biological progression  
**Initial Prototype:** Stage 1 - Single Cell Survival  
**Status:** In Progress

This document defines the technical implementation plan for the first playable prototype.

---

## Vision Summary

Play as a single bacterium in a microscopic world, fighting viruses and other threats. Gather resources, reproduce, and eventually infect larger organisms. The core experience: **weak but clever** - you program your cell to survive.

See `GDD.md` for full game design details.

### Development Goals
- **Stage 1:** Single-cell survival with programmable components (current focus)
- **Stage 2:** Infection mechanics (post-prototype)
- **Stage 3:** Planetary automation (post-prototype)

---

## Prototype Scope (Stage 1: "Primordial")

The first playable version focuses purely on single-cell gameplay:

### Core Experience
1. **World:** A small petri-dish/microscopic environment 
2. **Player:** One bacterial cell with programmable internals
3. **Resources:** Glucose, amino acids, ions floating in the environment
4. **Threats:** Viruses and predatory cells (optional for first iteration)
5. **Goal:** Gather resources, survive, and optionally reproduce once

### Mechanics
- **Movement:** WASD keyboard + click-to-move navigation
- **Gathering:** Phagocytosis (engulf resources)
- **Programming:** Simple component system (subset of full design)
- **Survival:** ATP/energy management

---

## Milestone 1: Foundation & Setup

### 1.1 Godot Project Setup
- [x] Configure project settings:
  - Resolution: 1280x720
  - Pixel-perfect 2D mode
  - Input map configuration
- [x] Set up project folder structure
- [x] Initialize git repository
- [x] Push to GitHub

### 1.2 Version Control
- [x] Create `.gitignore` for Godot projects
- [x] Initial commit with project structure
- [x] Push to origin remote

---

## Milestone 2: Player Cell

### 2.1 Input System
Configure Input Map:
- `move_up` - W / Up arrow
- `move_down` - S / Down arrow
- `move_left` - A / Left arrow
- `move_right` - D / Right arrow
- `click_move` - Left mouse button
- `toggle_programming` - Tab (open/close programming view)
- `phagocytosis` - Space / E (try to engulf)

### 2.2 Player Character Scene
- [ ] Create `Cell` scene (CharacterBody2D base)
- [ ] Cell membrane sprite (circle/blob shape)
- [ ] WASD movement with smooth acceleration
- [ ] Click-to-move with Navigation2D
- [ ] Cell faces movement direction

### 2.3 Internal State (Simplified)
- [ ] **ATP** - Energy currency (0-100 max)
- [ ] **ATP battery** - Stored energy (larger max)
- [ ] **Health/Membrane integrity** - Damage causes leaks
- [ ] Resource inventory: Glucose, Amino Acids, Ions

---

## Milestone 3: Environment & Resources

### 3.1 World
- [ ] Circular world boundary (petri dish metaphor)
- [ ] Background: Microscopic fluid with parallax particles
- [ ] Soft gradient lighting

### 3.2 Resources

| Resource | Visual | Gathering Method |
|----------|--------|------------------|
| **Glucose** | Small hexagonal particles | Absorb directly |
| **Amino Acids** | Small chain-like particles | Absorb directly |
| **Ions** | Tiny glowing dots | Absorb directly |
| **Viruses** | Spiky geometric shapes | Avoid/destroy |

### 3.3 Resource Mechanics
- [ ] Resources spawn randomly and drift slowly
- [ ] Click resource to move toward it
- [ ] Absorption when touching (or use Space to engulf)
- [ ] Convert Glucose to ATP
- [ ] Amino acids = building material for components

---

## Milestone 4: Component System (Prototype Version)

### 4.1 Implemented Components (Subset)

| Component | Function | Space Cost |
|-----------|----------|------------|
| **Mitochondria** | Converts Glucose → ATP | 2x2 |
| **Vacuole** | Stores Amino Acids | 1x1 |
| **Flagellum** | Movement (consumes ATP) | 1x2 |
| **Ion Channel** | Passive resource absorption | 1x1 |
| **Chemoreceptor** | Detects resources nearby | 1x1 |

### 4.2 Programming UI (Visual)
- [ ] Grid layout representing cell interior space
- [ ] Drag-and-drop component placement
- [ ] Simple connections: Output → Input
- [ ] Energy budget display
- [ ] Component shop/crafting (spend Amino Acids to build)

---

## Milestone 5: UI & Game Flow

### 5.1 Title Screen
- [ ] "Those of We" title
- [ ] Start Game → drops into petri dish world
- [ ] (Optional) Settings

### 5.2 HUD
- [ ] ATP gauge (current + storage)
- [ ] Resource counters (Glucose, Amino Acids, Ions)
- [ ] Membrane integrity bar
- [ ] Mini programming toggle button

### 5.3 Programming Overlay
- [ ] Full-screen or side-panel programming grid
- [ ] Component palette (drag from here)
- [ ] Current energy budget vs consumption
- [ ] Close with Tab or X button

### 5.4 Death & Respawn
- [ ] Membrane integrity hits 0 = death
- [ ] Simple "You dissipated" message
- [ ] Respawn at center, lose some resources

---

## Milestone 6: Threats (Optional for Prototype)

### 6.1 Viruses
- [ ] Spawn periodically
- [ ] Seek player cell
- [ ] Contact = code disruption (lose programming temporarily)
- [ ] Outrun them or use environment

### 6.2 Predatory Cells
- [ ] Larger NPC cells that roam
- [ ] Can engulf player
- [ ] Avoid or gang up on (if reproduction added)

---

## Development Phases

### Phase 1: Skeleton (Days 1-3)
1. ~~Godot setup + project structure~~ ✓
2. Basic cell movement (WASD + click)
3. Simple world with boundary
4. Placeholder sprites (colored circles)
5. ATP stat (number on screen)

### Phase 2: Core Loop (Days 4-7)
1. Resource spawning and absorption
2. ATP conversion from resources
3. Mitochondria component (simple passive)
4. Flagellum component (speed boost costs ATP)
5. Basic UI showing stats

### Phase 3: Programming (Days 8-12)
1. Programming grid UI
2. Component placement system
3. Component connections/activation
4. Energy budget calculation
5. Building new components from resources

### Phase 4: Polish (Days 13-17)
1. Generate art with Gemini
2. Integrate sprites and animations
3. Add particle effects
4. Title screen and game flow
5. Sound placeholders (if time)

### Phase 5: Playtest (Days 18-21)
1. Balance resource spawn rates
2. Tune ATP costs
3. Fix bugs
4. Add tutorial hints

---

## Technical Notes

### Godot Features to Use
- `CharacterBody2D` for cell physics
- `NavigationAgent2D` for click-to-move
- `TileMap` for background elements
- `Control` nodes for programming UI
- `Resource` for component definitions
- `Tween` for membrane animations

### Performance
- Limit resources on screen (~50 max)
- Despawn old resources
- Use `YSort` for proper layering
- Avoid physics bodies for small particles (use Area2D)

---

## Future (Post-Prototype)

Not in scope but on the roadmap:
- **Reproduction:** Cell division, colony formation
- **Infection:** Taking over multicellular organisms
- **Full component library:** Processing, sensors, logic gates
- **Viruses:** Complex threats with code injection
- **Evolution/tech tree:** Unlock new capabilities
- **Scale transitions:** Bacteria → tissue → organism

---

*Last Updated: 2026-04-15*  
*See also: `GDD.md` (design), `ASSETS.md` (art), `combat.md` (mechanics)*
