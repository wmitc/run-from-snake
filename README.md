# run-from-snake

Remember the game of snake? In this game you are the food. Run from the snake!

Classic Snake, inverted — **you're the apple.** An AI snake hunts you around a walled
grid arena, and every pellet you grab makes it longer and faster. Your own success
feeds the thing chasing you.

## Play

Open `index.html` in any browser. No build, no dependencies, one file.

- **Move:** arrow keys or WASD (hold to move, four directions, instant turns)
- **Goal:** collect pellets for score
- **The catch:** every pellet adds a segment to the snake and speeds it up
- **Death:** touching the snake — head or body
- **Music:** procedural chiptune that speeds up as you score — **M** to mute
- **Pause:** **P** (alt-tabbing away auto-pauses)
- **Bonus pellets:** a golden 5× score gamble near the snake's body, plus
  steady power-ups on open ground — cyan diamond = speed boost, violet ring =
  ghost (walk through the snake, but don't be inside it when it wears off),
  ice crystal = freeze all snakes for a moment, orange hourglass = slow every
  snake to half pace. The side panel has a key for all of them.

You're slightly faster than the snake and can turn instantly while it commits to its
path. Bait it into corners. Use its body as a wall. Steer your enemy.

## Escalation

The snake gets smarter as you score, and each upgrade is announced on screen:

- **10 pellets — "the snake grows cunning":** until now the snake is purely
  greedy — it steps straight toward you and gets stuck behind its own body,
  so it's easy to fake out. From here, every other move uses real pathfinding
  (BFS) that routes around obstacles.
- **15 pellets — "another one.":** a second, shorter snake joins the hunt. It
  stays permanently greedy and starts a bit slower than the veteran.
- **20 pellets — "it sees your paths":** pathfinding becomes the default — 3
  of every 4 moves take the true shortest path around walls and its own
  coils. Only the remaining greedy moves can still be juked, briefly.
