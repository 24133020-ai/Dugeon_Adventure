# Dungeon Adventure

Dungeon Adventure is a 2D roguelike dungeon-crawler built with Python and the Pygame library. Developed for an Artificial Intelligence course, this project demonstrates how various AI algorithms can be directly integrated into core gameplay systems—such as procedural generation, item optimization, and puzzle solving—rather than just enemy pathfinding.

---

### Gameplay & Rules

* **Explore:** Move through the dungeon, clear the fog of war, and collect all 4 hidden keys.
* **Unlock Minimap:** Locate the Laboratory Room and interact with it to permanently unlock the minimap navigation view.
* **Decrypt the Gate:** Head to the Warden Gate and stand near it to let the automated Backtracking CSP algorithm unlock the boss entrance.
* **Final Battle:** Enter the portal and defeat the Dungeon Boss in a strategic game of Gomoku (Five-in-a-Row) to win the game.

#### Item System:
* **Health Potion:** Instantly restores the player's health to maximum upon pickup.
* **Torch:** Grants a visibility boost (+3 blocks) to pierce through the dark fog of war.
* **Sword:** Grants melee combat capabilities (+1 Attack Power per sword found) to fight enemies.
* **Spirit:** A tactical scouting companion that flies out to explore unrevealed paths. If it finds a key, it reveals its location; otherwise, it disappears after 80 steps.

#### Keybindings & Controls:
* `W, A, S, D` or `Arrow Keys`: Move your character.
* `Spacebar`: Swing your sword to attack / Stop the Spirit camera tracking view.
* `I`: Open or close your Inventory screen.
* `E`: Pick up items on the ground / Interact with the Laboratory control panel.
* `M`: Toggle the Minimap on or off (Only works after clearing the Laboratory Room).
* `1` to `5`: Quick-use slots for inventory items.
* `R`: Instantly restart the game and generate a brand-new random dungeon layout.

---

### Integrated AI Algorithms

| AI Algorithm | Implemented File | Functional Gameplay Responsibility |
| :--- | :--- | :--- |
| **DFS Recursive Backtracking** | `maps/maze_generator.py` | Procedurally carves out a fully connected maze grid layout. |
| **Simulated Annealing** | `ai/simulated_annealing.py` | Optimizes the safe placement of special rooms (Boss, Lab, Key 4). |
| **Hill Climbing** | `ai/hill_climbing.py` | Scatters item drops evenly across remote tiles to avoid cluttering. |
| **Uniform Cost Search (UCS)** | `ai/ucs.py` | Computes and draws the absolute shortest navigation path from the Lab to the Boss Gate. |
| **Breadth-First Search (BFS)** | `ai/bfs.py` | Validates dungeon reachability and maps out paths for the scouting Spirit. |
| **Greedy Best-First Search** | `ai/greedy.py` | Drives real-time enemy pursuit behaviors based on Manhattan Distance. |
| **A* Search** | `ai/astar.py` | Controls elite enemy tracking routines using optimal step cost. |
| **Forward Checking** | `ai/forward_checking.py` | Animates and solves the real-time lock-picking puzzle at the Warden Gate. |
| **Min-Conflicts** | `ai/min_conflicts.py` | Drives the Tactical Advisor system to give strategic advice to the player. |
| **Minimax & Alpha-Beta** | `ai/minimax.py` | Acts as the decision-making brain of the Gomoku Boss during the final battle. |

---

### Project Structure

```text
AI_Dungeon_Adventure/
│
├── ai/                         # Core academic AI solvers (A*, UCS, Minimax, CSP modules)
├── assets/                     # Character graphics, item sprites, custom UI fonts, and sounds
├── game/                       # Entity controllers (Player, Inventory, Base Enemies, Traps)
├── maps/                       # Procedural generation pipelines, Fog of War, and custom arenas
├── systems/                    # Core managers (Combat loops, Laboratory interactions, Puzzle triggers)
├── ui/                         # Rendering canvases (HUD bars, Inventory screens, Game Over states)
├── AI_USAGE.md                 # Technical breakdown documentation of AI integration
├── PROJECT_CONTEXT.md          # Project boundaries, rules, and course scope context
├── STRUCTURE.md                # System interaction blueprints and layout mappings
├── TASK_LIST.md                # Component checklists and development logs
├── config.py                   # Game application settings and global constants
└── main.py                     # Primary runtime engine and application entry point
