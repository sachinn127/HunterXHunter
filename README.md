Console Game Engine in C++ (ECS)

This project is a simple console-based game written in C++ that demonstrates the Entity–Component–System (ECS) architecture.
The game runs on a 10×10 grid where the player can move, attack enemies, and see the game state update in real time through the terminal.
All objects in the game are represented as entities, which are just integer IDs. Data such as position, health, and weapons are stored separately as components,
while all game logic is handled by systems. This clear separation keeps the code clean, flexible, and easy to extend.
The engine includes systems for input handling, player movement, combat, rendering, and cleanup of defeated enemies.
The main game loop continuously renders the grid, processes input, updates game logic, and removes enemies with zero health until the player quits.
Although the gameplay is minimal, the project focuses on clean design and modern game-engine structure. It serves as a solid foundation 
for learning ECS concepts and can be easily extended with features like enemy AI, more weapons, or larger maps.

-----------------------------------------------------------------------------------
Movement System – moving the player

This system:
Looks only at the player
Checks what key you pressed
Moves the player accordingly
It also makes sure you don’t walk outside the grid.
-----------------------------------------------------------------------------------
Combat System – attacking enemies

When you press space:
The game checks where the player is
It checks where enemies are
If an enemy is close enough → it gets damaged
Only one enemy is hit per attack, like a simple melee strike.
Enemies don’t fight back — they just stand there waiting
-----------------------------------------------------------------------------------

Render System – drawing the game

This system:
Clears the console
Builds a fresh 10×10 grid
Places:
P where the player is
E where enemies are
. everywhere else
At the bottom, it also shows your current HP.
Every loop, the screen is redrawn so it feels like movement.
-----------------------------------------------------------------------------------
Engine – the manager

The Engine class ties everything together.
Initialization
When the game starts:
Player is created at the center
3 enemies are spawned at random places
Player gets a weapon
-----------------------------------------------------------------

Game Loop (this runs forever)

The game keeps repeating these steps:
Draw the screen
Ask for input
Move the player
Attack if needed
Remove dead enemies
This loop continues until you press q.
-------------------------------------------------------------------

Cleanup – removing dead enemies

If an enemy’s health reaches 0:
It is removed from the game
It disappears from the grid
The player is never removed.

