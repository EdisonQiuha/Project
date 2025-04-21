
# 360° Pixel Shooter - Infinite Shooter
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![Pygame 2.0](https://img.shields.io/badge/pygame-2.0-green.svg)](https://www.pygame.org/)

<div align="center">
  <img src="screenshots/gameplay.gif" width="800" alt="Game Demo">
</div>

## 📜 Table of Contents
- [Core Features](#✨-core-features)
- [Installation Guide](#🛠️-installation-guide)
- [Game Mechanics](#🎮-game-mechanics)
- [System Architecture](#🏗️-system-architecture)
- [Development Guide](#👨💻-development-guide)
- [Contributing](#🤝-contributing)
- [License](#⚖️-license)

## ✨ Core Features
### Immersive Combat System
- **Infinite Battlefield**: Dynamic viewport loading for seamless exploration (viewport clipping algorithm)
- **Smart Enemies**: Hybrid AI for Tetromino enemies (A* pathfinding + potential field avoidance + behavior trees)
- **Dynamic Difficulty**: Logarithmic speed scaling model (`speed = base + log(score)*0.3`)

### Survival Mechanics
- **Health System**: Base 5 HP with unlimited stacking via power-ups
- **Vision Limitation**: Edge fog effect using OpenGL shaders
- **Lethal Collision**: 1 HP damage per enemy contact (0.1px detection accuracy)

### Power-up System
| Type            | Duration   | Activation       |
|-----------------|------------|------------------|
| Triple Shot     | 15s        | Immediate        |
| Invincibility   | 10s        | Auto-trigger     |
| Health Boost    | Permanent  | Instant Apply     |

## 🛠️ Installation Guide
### Requirements
```bash
# Core dependencies
pip install pygame==2.1.3 
pip install pyopengl==3.1.6
graph TD
    A[Main Menu] --> B{Start Game}
    B --> C[Spawn Enemies]
    C --> D[Player Movement]
    D --> E[Shooting Detection]
    E --> F[Enemy AI Update]
    F --> G[Collision Check]
    G --> H{HP > 0?}
    H -->|Yes| C
    H -->|No| I[Game Over]
.
├── core/                 # Game Core
│   ├── entities/         # Game Entities
│   │   ├── player.py     # Player State Machine
│   │   └── enemy.py      # Tetromino AI
│   ├── systems/          # Subsystems
│   │   ├── collision.py  # Layered Collision Detection
│   │   └── scoring.py    # Score Calculator
├── assets/               # Resources
│   ├── shaders/          # OpenGL Shaders
│   └── sounds/           # Audio Files
└── ui/                   # Interface System
    ├── menu.py           # Menu Management
    └── hud.py            # Real-time HUD
We welcome contributions through:

Submitting issues for bug reports
Creating feature branches via fork
Ensuring PRs meet:
Passing unit tests (pytest tests/)
PEP8 compliance
Updated documentation
[Gameplay]
initial_health = 5       ; Starting HP
spawn_radius = 1500      ; Enemy spawn radius
fog_density = 0.7        ; Edge fog intensity

### Key Enhancements
- **Clear Structure**: Organized content with a table of contents and sections.
- **Technical Details**: Included specifics on mechanics and architecture.
- **Visual Aids**: Used badges and diagrams for better readability.
- **Bilingual Capability**: Prepared for future translations if needed.

Feel free to copy and paste this formatted content into your `README.md` file!
