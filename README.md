# UnrealExamPlatformer

*Arena platformer game made with Unreal Engine 5 via Blueprints*

![Unreal Engine 5](https://img.shields.io/badge/Unreal%20Engine-5-0E1128?logo=unrealengine&logoColor=white)
![Blueprints](https://img.shields.io/badge/Scripting-Blueprints%20only-4C4CFF)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/status-complete%20(editor)%2C%20build%20broken-orange)

---

## 🔎 overview/

UnrealExamPlatformer is a Super Mario–inspired arena platformer built solo in **10 days** as the second-year Unreal Engine exam for the "Video Game Programming" course at AIV. The brief was simple on paper: prove you can use the engine end-to-end using *only* Blueprints — no C++.

Players clear each level by collecting all coins and defeating all enemies, picking up powerups dropped by dead enemies or smashed question blocks along the way, then reaching the end-of-level flag to win.

What this project was really about wasn't the platformer itself — it was forcing a broad pass across the engine in a short window: general engine literacy, more advanced Blueprint scripting, animation via graphs, medium-complexity AI, and basic UI, all under a hard deadline.

- **What I learned:** how to build a complete, playable game in Unreal Engine touching every major development discipline (animation, AI, UI, gameplay systems) in a tight timeframe.
- **Status:** Feature-complete and fully playable in-editor. The packaged build does not behave correctly — see the Technical section.

---

## 🕹️ functional/

### Tech stack
- **Engine:** Unreal Engine 5
- **Scripting:** Blueprints exclusively (no C++), by design constraint of the exam
- **Systems covered:** Animation Blueprints/graphs, AI (enemy behavior logic), UMG-based UI

### Controls
| Input | Action |
|---|---|
| `W` `A` `S` `D` | Movement |
| `Spacebar` | Jump |

### How to play
The recommended way to try the game is **"Launch Game" from within the Unreal Editor**, not a packaged build — the exam was tested and validated exclusively in-editor.

> ⚠️ **Known issue:** The packaged/standalone build produces unexpected results and hasn't been fixed. Some mechanics may not behave correctly outside the editor. See [Technical](#⚙️-technical) for details.

### Media
![Gameplay preview 1](https://github.com/user-attachments/assets/241a2726-b873-4f69-b39e-a712192dffb5)


![Gameplay preview 2](https://github.com/user-attachments/assets/51e72adf-a803-4a3a-899e-96cf7e465caf)


### Playable build
Not available — the project is playable only via the Unreal Editor.

---

## ⚙️ technical/

### Architecture
Everything is implemented in Blueprints, structured around the core gameplay loop of a linear platformer level: player character with movement/jump, enemy AI actors, collectible coins, destructible "question blocks" that spawn powerups, and an end-of-level flag trigger that advances/completes the level. Animation state is handled through Animation Blueprints driving movement and combat/hit reactions, and enemy behavior sits at a "medium" AI complexity level — enough to patrol/react and pose a real threat without a full utility-AI setup.

### Hardest decision
The toughest call was going all-in on Blueprints-only architecture instead of reaching for even minimal C++ helper classes, despite knowing it would make some systems (enemy AI state handling, powerup spawning logic) more verbose and harder to debug visually. It was the right call given the exam's explicit goal — proving Blueprint fluency — but it meant accepting slower iteration and messier node graphs in exchange for staying true to the assignment's constraints.

### What didn't work
Packaging the project into a standalone build produces unexpected/incorrect results compared to running it in the editor. The root cause hasn't been identified yet — the issue remains open, and the game should currently be considered "editor-only" in terms of guaranteed correctness.

### Testing
Validated manually through iterative in-editor playtesting across all levels (coin collection, enemy kills, powerup drops, block destruction, flag trigger); no build-level testing was completed due to the packaging issue above.
