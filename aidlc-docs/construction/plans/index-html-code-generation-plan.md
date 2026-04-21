# Code Generation Plan - index.html (Flappy Mauri)

## Unit Context
- **Unit**: index.html — single self-contained browser game file
- **Output path**: `/Users/nicobxez/Desktop/aws-kiro-workshop/index.html`
- **Assets (relative paths)**: `assets/ghosty.png`, `assets/jump.wav`, `assets/game_over.wav`
- **Dependencies**: None (vanilla JS, no libraries)

## Requirements Traceability
| Requirement | Description |
|---|---|
| FR-01 | Ghosty sprite, gravity, spacebar jump, jump.wav |
| FR-02 | Spooky-themed wall pairs, random gap heights, scrolling |
| FR-03 | Score +1 per wall pair, localStorage best score |
| FR-04 | Collision detection, game_over.wav, Game Over screen, spacebar restart |
| FR-05 | Difficulty scaling — wall speed increases with score |
| FR-06 | Start screen on first load |
| FR-07 | Day/night cycle — gradual background and wall colour transition |
| NFR-01 | Vanilla HTML5 Canvas + JS, single file, no server |
| NFR-02 | Relative asset paths |
| NFR-03 | 60fps requestAnimationFrame, off-screen wall recycling |
| NFR-04 | Chrome, Firefox, Safari compatible |

---

## Generation Steps

- [x] **Step 1 — HTML scaffold**: Create `index.html` with `<canvas>`, asset `<img>` and `<audio>` tags, and a `<script>` block
- [x] **Step 2 — Game constants**: Define canvas size, gravity, jump velocity, wall width, gap size, base speed, speed increment, day/night cycle duration
- [x] **Step 3 — Asset loading**: Load `ghosty.png` via Image, `jump.wav` and `game_over.wav` via Audio
- [x] **Step 4 — Game state**: Variables for Ghosty position/velocity, walls array, score, best score (localStorage), game phase (start/playing/gameover), day/night cycle progress
- [x] **Step 5 — Input handling**: Spacebar keydown → jump during play, start game on start screen, restart on game over screen
- [x] **Step 6 — Wall logic**: Spawn wall pairs with random gap Y, scroll left each frame, recycle off-screen walls, increment score on pass
- [x] **Step 7 — Day/night cycle**: Time-based `cycleT` (0→1 day→night→day), lerp background colour and wall colour tint each frame
- [x] **Step 8 — Collision detection**: AABB check Ghosty vs each wall segment and ground
- [x] **Step 9 — Rendering**: Draw background (day/night colour), walls (spooky tinted), Ghosty sprite, score HUD, start screen overlay, game over overlay
- [x] **Step 10 — Game loop**: `requestAnimationFrame` loop calling update + render; delta-time capped to prevent spiral of death
- [x] **Step 11 — Difficulty scaling**: Increase wall scroll speed by a small step every N points scored
