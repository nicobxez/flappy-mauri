# Integration Test Instructions — Flappy Mauri

Flappy Mauri is a single-file client-side game with no backend services. Integration testing focuses on the interactions between the game's internal subsystems and the browser APIs it depends on.

---

## Scenario 1: Asset Loading → Rendering

**What is tested**: ghosty.png loads correctly and renders on canvas.

1. Open `index.html`
2. Start the game (Space)
3. **Expected**: Ghosty appears as the sprite image, not a white fallback rectangle

---

## Scenario 2: Audio → Game Events

**What is tested**: Audio files trigger at the correct game events.

1. Start the game
2. Press Space — **Expected**: `jump.wav` plays
3. Collide with a wall — **Expected**: `game_over.wav` plays
4. Restart and collide with the ground — **Expected**: `game_over.wav` plays again

---

## Scenario 3: Score → localStorage Persistence

**What is tested**: Best score survives a page reload.

1. Play and achieve a score of at least 3
2. Collide (game over) — note the score shown
3. Close and reopen `index.html`
4. Play and die immediately (score 0)
5. **Expected**: Game Over screen shows the previous best score, not 0

---

## Scenario 4: Score → Difficulty Scaling

**What is tested**: Wall speed increases as score rises.

1. Play until score reaches 5
2. **Expected**: Walls noticeably scroll faster than at score 0
3. Continue to score 10
4. **Expected**: Walls scroll faster again

---

## Scenario 5: Day/Night Cycle → Wall Colour

**What is tested**: Wall colour responds to the day/night cycle state.

1. Play for ~12 seconds (one half-cycle)
2. **Expected**: Background is dark (night); walls are very dark purple
3. Play for another ~12 seconds
4. **Expected**: Background is bright (day); walls return to normal purple
