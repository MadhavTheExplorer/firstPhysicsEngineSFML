# SFML Verlet Physics Engine

A small C++/SFML visualization that simulates colored circles under gravity using Verlet integration, pairwise overlap resolution, and circular boundary confinement.

## What It Demonstrates

- Fixed-step particle motion using current and previous positions.
- Gravity and acceleration integration without an explicit velocity state.
- Pairwise circle-overlap detection and positional collision correction.
- Circular world-boundary constraints.
- SFML rendering, event handling, randomized radii, and color variation.

The executable gradually spawns up to 400 circles in a fullscreen 1920 x 1080 window. Press `Escape` to exit.

## Repository Map

| Area | Contents |
| --- | --- |
| `src/main.cpp` | Application setup, spawn loop, simulation update, and rendering. |
| `src/solver.cpp` | Physics update and constraint solving. |
| `src/events.cpp` | Window event handling. |
| `inc/solver/` | Solver interface. |
| `inc/renderer/` | SFML drawing helpers. |
| `inc/game/physics/` | Physics object definitions. |

## Build And Run

Requirements:

- CMake 3.28 or newer
- A C++ compiler compatible with the SFML 3.0.0 binaries for your platform
- Git/network access during the first configure, because CMake FetchContent downloads SFML

```bash
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release
```

Run the `Tut1` executable from `build/bin` or the configuration-specific output directory created by your generator.

## Limitations

Collision detection checks every particle pair and therefore scales as $O(n^2)$. The display dimensions and particle limit are fixed in source, and the project currently has no automated physics tests.

SFML is an external dependency distributed under its own license. This repository does not currently declare a license for the project source.

## Portfolio Metadata

`.explorer/project.yml` classifies this archived learning project in the `simulation-and-modeling` family.