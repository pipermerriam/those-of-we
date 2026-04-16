# Those of We

A factory automation game with biological progression.

Built with Godot 4.x

## Setup

1. Install Godot 4.x: https://godotengine.org/download
2. Open this folder (`game/`) in Godot
3. Press Play (F5) to run

## Project Structure

```
res://
├── assets/
│   ├── art/
│   │   ├── cells/      # Player and enemy cell sprites
│   │   ├── resources/  # Glucose, amino acids, ions
│   │   ├── environment/# Background, particles
│   │   ├── components/ # Component icons for UI
│   │   ├── ui/         # Interface elements
│   │   └── vfx/        # Particle effects
│   ├── audio/
│   └── fonts/
├── scenes/
│   ├── ui/
│   ├── cells/
│   ├── environment/
│   ├── components/
│   └── _autoload/
├── scripts/
│   ├── systems/
│   └── utils/
└── resources/
```

## Documentation

- `../README.md` - Game design document
- `../PLAN.md` - Implementation plan and milestones
- `../ASSETS.md` - Art asset specifications
- `../combat.md` - Combat mechanics deep-dive
