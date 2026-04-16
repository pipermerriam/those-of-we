# Those of We - Game Project

Built with Godot 4.x

## Quick Start

```bash
# From this directory
godot .  
# Or open project.godot in Godot editor
```

## Project Structure

```
res://
├── assets/
│   ├── art/
│   │   ├── cells/       # Player and enemy cells
│   │   ├── resources/   # Glucose, amino acids, ions
│   │   ├── environment/ # Backgrounds, particles
│   │   ├── components/  # Component UI icons
│   │   ├── ui/          # Interface elements
│   │   └── vfx/         # Particle effects
│   ├── audio/
│   └── fonts/
├── scenes/
│   ├── ui/
│   ├── cells/
│   ├── environment/
│   ├── components/
│   └── _autoload/       # Singletons/autoloads
├── scripts/
│   ├── systems/
│   └── utils/
└── resources/           # Godot Resource definitions
```

## Documentation

See `../docs/` for all design and planning documents:
- `GDD.md` - Game Design Document
- `PLAN.md` - Implementation plan and milestones
- `ASSETS.md` - Art asset specifications
- `combat.md` - Combat mechanics deep-dive

---

*For contributing guidelines and project setup, see `../README.md`*
