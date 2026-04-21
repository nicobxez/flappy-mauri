# Manual Test Instructions — Flappy Mauri

No automated test framework is used (vanilla JS, single file). All tests are manual browser checks.

Open `index.html` in the browser and execute each scenario.

---

## FR-01 — Ghosty / Controls

| # | Action | Expected |
|---|---|---|
| 1.1 | Open the file | Start screen shown with title and prompt |
| 1.2 | Press Space | Game starts; Ghosty visible using ghosty.png sprite |
| 1.3 | Do nothing | Ghosty falls due to gravity |
| 1.4 | Press Space during play | Ghosty jumps upward; jump sound plays |
| 1.5 | Tap canvas on mobile/touch | Same as Space — Ghosty jumps |

## FR-02 — Walls

| # | Action | Expected |
|---|---|---|
| 2.1 | Watch walls appear | Pairs scroll from right to left |
| 2.2 | Observe gap positions | Each pair has a different random gap height |
| 2.3 | Observe wall style | Dark spooky purple with cap decorations |

## FR-03 — Scoring

| # | Action | Expected |
|---|---|---|
| 3.1 | Pass through a gap | Score counter at top increments by 1 |
| 3.2 | Die, then reopen file | Best score persists (localStorage) |

## FR-04 — Collision & Game Over

| # | Action | Expected |
|---|---|---|
| 4.1 | Fly into a wall | Game over sound plays; Game Over screen shown |
| 4.2 | Fall to the ground | Same as 4.1 |
| 4.3 | Game Over screen | Shows current score and best score |
| 4.4 | Press Space on Game Over | Returns to start screen |

## FR-05 — Difficulty Scaling

| # | Action | Expected |
|---|---|---|
| 5.1 | Reach score 5 | Walls visibly scroll faster |
| 5.2 | Reach score 10 | Walls scroll faster again |

## FR-06 — Start Screen

| # | Action | Expected |
|---|---|---|
| 6.1 | Load page | Start screen overlay shown before any gameplay |

## FR-07 — Day/Night Cycle

| # | Action | Expected |
|---|---|---|
| 7.1 | Play for ~12 seconds | Background gradually darkens to night |
| 7.2 | Play for ~24 seconds | Background gradually brightens back to day |
| 7.3 | Observe walls during night | Wall colour darkens proportionally |
| 7.4 | Observe walls during day | Wall colour returns to normal purple |

## NFR-03 — Performance

| # | Action | Expected |
|---|---|---|
| 8.1 | Open browser DevTools → Performance | Game loop runs at ~60 fps |
| 8.2 | Play for 2+ minutes | No slowdown; off-screen walls are recycled |

## NFR-04 — Browser Compatibility

| # | Browser | Expected |
|---|---|---|
| 9.1 | Chrome latest | All features work |
| 9.2 | Firefox latest | All features work |
| 9.3 | Safari latest | All features work |
