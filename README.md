# Those of We

A factory automation game with biological progression.

Built with Godot 4.x.

---

## Quick Start

### Prerequisites

* Godot 4.6+ - [Download](https://godotengine.org/download) or install via:
  ```bash
  # Download and install to ~/bin (Linux)
  mkdir -p ~/bin
  cd ~/bin
  curl -L -o godot.zip "https://github.com/godotengine/godot/releases/download/4.6.2-stable/Godot_v4.6.2-stable_linux.x86_64.zip"
  unzip godot.zip
  ln -sf Godot_v4.6.2-stable_linux.x86_64 godot
  export PATH="$HOME/bin:$PATH"
  ```
* Git

### Clone and Run

```bash
# Clone the repository
git clone git@github.com:pipermerriam/those-of-we.git
cd those-of-we

# Run from command line (ensure godot is on your PATH)
cd game
godot .

# Or open in Godot editor
godot --editor .
```

### First Time Setup

When you first run the project, Godot will automatically import all assets. This may take a moment.

### Controls

* **WASD** - Move the player character
* **ESC** - Pause

### Build (Export)

```bash
cd game
godot --headless --export-release "Linux/X11" ../build/those-of-we.x86_64
```

---

## Project Structure

```
those-of-we/
├── game/            # Godot project root
│   ├── assets/      # Art, audio, fonts
│   ├── scenes/      # Godot scene files
│   ├── scripts/     # GDScript source
│   ├── resources/   # Resource definitions
│   └── project.godot
├── docs/            # Design documents
└── README.md        # This file
```

---

## Documentation

* `docs/GDD.md` - Game Design Document (core concepts, mechanics, progression)
* `docs/PLAN.md` - Implementation plan and milestones
* `docs/ASSETS.md` - Art asset specifications
* `docs/combat.md` - Combat mechanics deep-dive

---

## Contributing

1. Create a feature branch: `git checkout -b feature/name`
2. Commit changes: `git commit -am "Add feature"`
3. Push to origin: `git push origin feature/name`
4. Open a pull request

---

## License

TBD
