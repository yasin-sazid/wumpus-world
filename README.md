# Wumpus World — Interactive Browser Game

A browser-based implementation of Wumpus World, the grid-world game associated with knowledge representation and intelligent-agent exercises. The project combines exploration, environmental cues, configurable worlds, and audiovisual feedback in an interactive p5.js experience.

## Gameplay features

- Explore a grid containing pits, gold, and a Wumpus.
- Read **breeze** and **stench** cues associated with nearby hazards.
- Move the agent, collect gold, and use its arrow.
- Adjust world size, pit density, and the number of gold items.
- Control sound volume and experiment with world auto-increment and cheat-mode options.

## Architecture

```text
Connect static server → Browser page → p5.js rendering
                                           |
                            World / Room / Agent objects
                                           |
                           Hazards, cues, gold, and sound
```

`app.js` serves the repository using Connect and `serve-static`. The browser implementation under `js/` separates the world, rooms, agent, hazards, and percepts into classes. `sketch.js` coordinates the p5.js lifecycle, and `misc.js` connects the settings controls to the world state.

The `assets/` directory supplies textures and sounds; `img/controls.png` provides the visual control guide.

## Run

Use Node.js and npm:

```bash
npm install
npm start
```

Open **`http://localhost:8080`**. The server also accepts a `PORT` environment variable. Use the interface's control guide to move, interact, and explore the generated world. Browser libraries referenced by `index.html` should be reachable when loading the page.

## Technical focus

The implementation connects an object-oriented world model with browser input, real-time rendering, spatial hazard cues, and configurable generation settings. Its small static-serving backend keeps the gameplay logic in inspectable browser-side modules.

## Contributors

Yasin Sazid (BSSE 1006), Atkia Akila Karim (BSSE 1015), and Abdullah-Al-Jahid (BSSE 1030).
