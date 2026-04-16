# Those of We - Art Asset Specification

_Prototype Art Requirements_

---

## Visual Style

**Aesthetic:** Microscopic world - petri dish aesthetic  
**Style:** Clean, slightly abstract/cellular biology look  
**Palette:**
- Background: Cool blue/cyan (#1a3a52, #2d5a7c with gradients)
- Resources: Warm yellows/oranges (#ffaa00, #ff8800)
- Threats: Red/purple (#cc3366, #993366)
- Player: Green/yellow membrane (#66cc99 with semi-transparency)

**Rendering:** Semi-transparent membranes, soft glows, particle effects

---

## Asset List

### Player Cell

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| CELL-001 | Cell Body | Circular membrane, translucent green | 128x128 | P0 |
| CELL-002 | Nucleus | Internal blob, darker green | 48x48 | P0 |
| CELL-003 | Membrane Damage 1 | Small cracks | 128x128 | P2 |
| CELL-004 | Membrane Damage 2 | Large tears | 128x128 | P2 |
| CELL-005 | Flagellum | Tail wiggling sprite sheet (4 frames) | 64x128 | P1 |
| CELL-006 | Absorption State | Membrane puckering animation | 128x128 | P2 |

### Resources

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| RES-001 | Glucose | Small yellow hexagon, soft glow | 32x32 | P0 |
| RES-002 | Amino Acids | Orange chain/links shape | 32x32 | P0 |
| RES-003 | Ion | Tiny cyan dot with pulse glow | 16x16 | P0 |
| RES-004 | Virus | Spiky geometric purple shape | 48x48 | P2 |

### Environmental

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| ENV-001 | Background Fluid | Tileable blue/cyan gradient | 512x512 | P0 |
| ENV-002 | Petri Dish Edge | Circular boundary rim | Ring texture | P1 |
| ENV-003 | Dust Mote 1 | Tiny floating particle | 8x8 | P2 |
| ENV-004 | Dust Mote 2 | Slightly larger particle | 16x16 | P2 |

### Components (for Programming UI)

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| COMP-001 | Mitochondria | Oval with internal folds, orange-yellow | 64x64 | P1 |
| COMP-002 | Vacuole | Round storage bubble, blue tint | 48x48 | P1 |
| COMP-003 | Flagellum Icon | Simplified tail shape | 48x48 | P1 |
| COMP-004 | Ion Channel | Ring/dot structure | 32x32 | P1 |
| COMP-005 | Chemoreceptor | Antenna/sensor shape | 32x32 | P1 |

### UI Elements

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| UI-001 | Title Background | Microscopic world vista | 1920x1080 | P1 |
| UI-002 | ATP Gauge Fill | Yellow bar segment | 32x8 | P0 |
| UI-003 | Membrane Gauge Fill | Green bar segment | 32x8 | P0 |
| UI-004 | Button Normal | Clean rounded rectangle | Variable | P1 |
| UI-005 | Programming Grid | Empty cell slot (square outline) | 64x64 | P1 |

### Effects

| ID | Name | Description | Size | Priority |
|----|------|-------------|------|----------|
| VFX-001 | Absorption Swirl | Particle effect frames | 64x64 | P2 |
| VFX-002 | ATP Spark | Small flash for energy gen | 32x32 | P2 |
| VFX-003 | Damage Burst | Membrane tear particles | 64x64 | P2 |
| VFX-004 | Selection Ring | Hover/selection indicator | 128x128 | P1 |

---

## Generation Prompts

### Cell Body
```
Top-down view of a single biological cell, circular shape, 
semi-transparent green membrane, internal organelle hints visible, 
soft shading, scientific microscopic style, 
isolated on transparent background, digital art
```

### Resources
```
{Glucose: small yellow hexagonal crystal, glowing center, 
biological resource particle, isolated on transparent background,
soft glow effect}
```

```
{Amino acids: orange chain of linked spheres, biological molecules,
scientific style, isolated on transparent background}
```

### Background
```
Seamless tileable texture of microscopic fluid, blue cyan gradient,
soft abstract organic shapes, petri dish aesthetic,
scientific biology background, clean digital art
```

---

## File Naming

```
{category}_{name}_{state}.png

cell_body_idle.png
cell_nucleus.png
cell_flagellum_sheet.png
res_glucose.png
res_amino_acid.png
res_ion.png
env_background_tile.png
ui_atp_bar.png
comp_mitochondria.png
vfx_absorb_swirl.png
```

---

## Storage

```
game/assets/art/
├── cells/
│   ├── player/
│   └── enemies/
├── resources/
├── environment/
├── components/
├── ui/
└── vfx/
```

---

*Reference: `PLAN.md` for prototype scope, `GDD.md` for design*
