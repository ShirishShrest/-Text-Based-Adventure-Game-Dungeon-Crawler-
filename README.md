# Dungeon Adventure Game

A text-based dungeon crawler game built for Jupyter Notebook with emoji graphics, turn-based combat, and intelligent AI monsters.

## Features

- Multiple Difficulty Levels: Easy, Medium, and Hard with different map layouts and monster configurations
- Turn-Based Combat: Attack monsters with weapons or your fists, with cooldown mechanics
- Intelligent AI: Monsters use pathfinding to chase the player and make strategic moves
- Inventory System: Collect weapons and health potions throughout the dungeon
- Quest System: Track your objectives with a built-in quest log
- Undo System: Made a mistake? Undo your last 5 actions
- Emoji Graphics: Colorful emoji-based visual representation of the game world

## Getting Started

### Prerequisites
- Python 3.6+
- Jupyter Lab/Notebook
- IPython

### Installation
1. Clone this repository or download the .ipynb file
2. Open Jupyter Lab/Notebook
3. Open the dungeon_game.ipynb file
4. Run all cells sequentially

### Quick Start
```python
# Create a new game (difficulty: "easy", "medium", or "hard")
game = Game(diff="easy")
game.run()
```

## How to Play

### Game Controls

Command                           | Description
----------------------------------|------------------------------------------
north, south, east, west (n/s/e/w)| Move in direction
attack                            | Attack adjacent monster
equip <item>                      | Equip a weapon from inventory
use <item>                        | Use a consumable item
inventory (inv, i)                | Show your inventory
quests (quest, q)                 | Display quest log
undo (u)                          | Undo last action
help (h, ?)                       | Show help menu
quit                              | Exit the game

### Game Elements

Symbol | Meaning
-------|-------------------
🧙     | Player character
🪨     | Wall/obstacle
⬛     | Empty floor
⚔️     | Sword weapon
🧪     | Health potion
👾     | Weak monster
👺     | Medium monster
👹     | Strong monster
💀     | Boss monster (hard mode)

## Game Mechanics

### Combat System
- Attack Damage: Depends on equipped weapon (Fists: 5, Sword: 40)
- Cooldown: 2 turns after attacking before you can attack again
- Monster AI: Enemies move toward player and attack when adjacent
- Health: Player starts with 100 HP, monsters vary by type

### Difficulty Levels

#### Easy Mode
- Small 15x11 map
- 3 monsters: 2x Weak (15 HP), 1x Strong (25 HP)
- Basic AI movement (30% intelligent, 70% random)

#### Medium Mode
- Medium 18x11 map
- 3 monsters: 1x Weak (20 HP), 1x Medium (35 HP), 1x Strong (50 HP)
- Standard AI movement (30% intelligent, 70% random)

#### Hard Mode
- Large 19x11 map
- 4 monsters including boss: Weak (25 HP), Medium (40 HP), Strong (60 HP), Boss (80 HP)
- Advanced AI movement (50-80% intelligent depending on monster)

### Items
- Health Potion: Restores 30 HP (max 100 HP)
- Sword: Increases attack damage to 40 (from 5 with fists)
- Starting inventory: 1 Health Potion

### Undo System
- Save up to 5 previous game states
- Undo movement, combat, item usage, and equipment changes
- Cannot undo if no previous states available

## Code Structure

The game is organized into the following classes:

### Core Classes
- `Quest` & `QuestLog`: Mission tracking system
- `Item`: Weapons and consumables
- `Entity`: Base class for all game objects

### Character Classes  
- `Player`: User-controlled character with inventory and combat
- `Monster`: AI-controlled enemies with pathfinding

### World Classes
- `AdventureMap`: Game world generation and display
- `Game`: Main controller handling game loop and user input

## Example Gameplay

```
🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨
🪨⬛⬛⬛⬛⬛🪨⬛⬛⬛🪨⬛⬛⬛⬛⬛🪨
🪨⬛⬛🪨⬛⬛🪨⬛🪨⬛🪨⬛⬛⬛⬛⬛🪨
🪨⬛⬛🪨⬛⬛⬛⬛⬛⬛⬛⬛🪨⬛⬛⬛🪨
🪨⬛🧙⬛⬛🪨🪨🪨⬛⬛🪨⬛⬛⬛⬛⬛🪨
🪨⬛⚔️⬛⬛⬛🪨⬛⬛⬛⬛⬛⬛⬛⬛⬛🪨
🪨⬛⬛🪨⬛⬛⬛🪨⬛⬛⬛🪨⬛⬛⬛⬛🪨
🪨⬛⬛🪨⬛⬛⬛⬛⬛⬛⬛⬛🪨⬛⬛⬛🪨
🪨⬛⬛⬛🪨⬛🪨🪨🪨⬛🪨⬛⬛⬛⬛⬛🪨
🪨⬛⬛⬛⬛⬛🧪🪨⬛⬛⬛⬛⬛⬛⬛⬛🪨
🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨🪨

⚔️ Weapon: 👊 Fists (⚔️ 5)
HP: ❤️❤️❤️❤️❤️❤️❤️❤️❤️❤️ (100/100)
📍 Position: (2, 4)
🎒 Inventory: 🧪 Health Potion
⏪ Undo: 1 available

📋 Quest Log:
📝 Defeat All Monsters: Clear the dungeon of all enemies

🔍 Items on map: ⚔️ at (2, 5), 🧪 at (6, 9)

🧿 Monsters:
👾 HP: ❤️❤️❤️❤️❤️❤️🖤🖤🖤🖤 (15/15) | 📏 8
👾 HP: ❤️❤️❤️❤️❤️❤️🖤🖤🖤🖤 (15/15) | 📏 12
👹 HP: ❤️❤️❤️❤️❤️❤️❤️❤️❤️❤️ (25/25) | 📏 6

> south
```

## Tips for Playing

1. **Collect the sword early** - It increases your damage from 5 to 40
2. **Save health potions** - Use them when your HP is low (below 30)
3. **Use the undo feature** - Don't be afraid to experiment and undo bad moves
4. **Watch monster distances** - Plan your route to avoid getting surrounded
5. **Attack cooldown matters** - Plan your attacks carefully since you can't attack for 2 turns after

## Contributing

Feel free to fork this project and submit pull requests for:
- New difficulty levels
- Additional items and weapons
- New monster types
- Enhanced AI behavior
- Visual improvements
