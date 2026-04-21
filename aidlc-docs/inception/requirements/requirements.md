# Flappy Kiro - Requirements Document

## Intent Analysis

- **User Request**: Build a Flappy Bird clone called Flappy Mauri using provided assets
- **Request Type**: New Project (Greenfield)
- **Scope**: Single-component browser game (one HTML file)
- **Complexity**: Moderate

---

## Functional Requirements

### FR-01: Player Character
- The player controls a ghost character named Ghosty
- Ghosty is rendered using the provided `assets/ghosty.png` sprite
- Ghosty moves persistently to the right (the world scrolls left)
- Ghosty falls automatically due to gravity
- Ghosty ascends when the player presses the spacebar (jump/flap)
- `assets/jump.wav` plays on each spacebar press

### FR-02: Obstacles (Walls)
- Walls appear as pairs (top and bottom) with a gap in the middle
- All gaps are equally sized
- Gap vertical position is randomised for each wall pair
- Walls have a spooky/ghost-themed visual style (dark colours)
- Walls scroll from right to left at a constant base speed

### FR-03: Scoring
- The player earns 1 point for each wall pair successfully passed
- Current score is displayed on screen during gameplay
- Best score is persisted across sessions using `localStorage`
- Both current score and best score are shown on the Game Over screen

### FR-04: Collision & Game Over
- Collision with any wall (top or bottom segment) ends the game
- Collision with the ground ends the game
- `assets/game_over.wav` plays on collision
- A Game Over screen is shown with the current score, best score, and a restart prompt
- The player can restart by pressing spacebar on the Game Over screen

### FR-05: Difficulty Scaling
- Wall scroll speed increases gradually as the player's score increases
- Speed increase is incremental (e.g., small step-up every N points)

### FR-06: Start Screen
- On first load, display a start screen prompting the player to press spacebar to begin

### FR-07: Day/Night Cycle
- The background alternates between a daytime state and a nighttime state on a fixed time interval
- The transition is gradual (smooth fade between day and night)
- During nighttime the background darkens to simulate night sky
- Wall colours darken proportionally during night and return to normal during day
- The cycle repeats continuously throughout gameplay

---

## Non-Functional Requirements

### NFR-01: Technology Stack
- Vanilla HTML5 Canvas + JavaScript — no external frameworks or libraries
- Single self-contained `index.html` file; opens directly in any modern browser without a server

### NFR-02: Asset Usage
- Sprite: `assets/ghosty.png` (loaded via `Image` object)
- Audio: `assets/jump.wav` and `assets/game_over.wav` (loaded via `Audio` object)
- Asset paths are relative so the file works from the project root

### NFR-03: Performance
- Game loop runs at 60 fps using `requestAnimationFrame`
- No memory leaks from unbounded object creation (recycle or remove off-screen walls)

### NFR-04: Compatibility
- Must run in current versions of Chrome, Firefox, and Safari without plugins

---

## Extension Configuration

| Extension | Enabled | Decided At |
|---|---|---|
| Security Baseline | No | Requirements Analysis (Q9: B) |

Security rules are not enforced — this is a client-side game prototype with no backend, data stores, or user authentication.
