# 2D Adventure Game

A Java-based 2D adventure game built with Swing graphics and featuring tile-based world exploration, NPC interactions, and object collection mechanics.

## 🎮 Game Overview

This is a top-down 2D adventure game where players control a character named "Lilius" who explores an island in search of treasure. The game features:

- **Tile-based world exploration** with a 50x50 world grid
- **NPC interactions** with dialogue system
- **Object collection** mechanics
- **Collision detection** for walls, water, and objects
- **Smooth character animation** with sprite-based movement
- **Sound effects and background music**
- **Pause and dialogue states**

## 🏗️ Project Structure

```
My2DGame/
├── src/
│   ├── main/           # Core game engine classes
│   ├── entity/         # Player and NPC classes
│   ├── object/         # Collectible objects
│   └── tile/           # Tile management and rendering
├── res/                # Game resources
│   ├── font/           # Custom fonts
│   ├── maps/           # World map files
│   ├── npc/            # NPC sprites
│   ├── objects/        # Object sprites
│   ├── player/         # Player character sprites
│   ├── sound/          # Audio files
│   └── tiles/          # Tile sprites
└── out/                # Compiled classes
```

## 🎯 Core Features

### Game Engine (`src/main/`)
- **GamePanel**: Main game loop, rendering, and state management
- **KeyHandler**: Input handling for WASD movement and game controls
- **CollisionChecker**: Comprehensive collision detection system
- **AssetSetter**: Object and NPC placement in the world
- **UI**: User interface rendering (pause screen, dialogue)
- **Sound**: Audio playback for music and sound effects
- **UtilityTool**: Image scaling utilities

### Entity System (`src/entity/`)
- **Entity**: Base class for all game entities with movement and rendering
- **Player**: Player character with interaction mechanics
- **NPC_Vlad**: Interactive NPC with dialogue and random movement

### Object System (`src/object/`)
- **SuperObject**: Base class for all collectible objects
- **OBJ_Key**: Key object for unlocking doors
- **OBJ_Door**: Door object with collision
- **OBJ_Chest**: Treasure chest object
- **OBJ_Boots**: Boots object (collectible)

### Tile System (`src/tile/`)
- **TileManager**: Handles tile loading, rendering, and collision
- **Tile**: Individual tile properties and collision flags

## 🎮 Controls

- **W/↑**: Move Up
- **S/↓**: Move Down
- **A/←**: Move Left
- **D/→**: Move Right
- **P**: Pause/Unpause Game
- **Enter**: Interact with NPCs
- **T**: Toggle Debug Draw Time (Development)

## 🌍 World Design

The game world is a 50x50 tile grid featuring:
- **Grass tiles** (walkable)
- **Water tiles** (collision)
- **Road tiles** (walkable)
- **Wall tiles** (collision)
- **Tree tiles** (collision)
- **Earth tiles** (walkable)

The world map is loaded from `res/maps/worldV2.txt` and contains various terrain types represented by numerical IDs.

## 🎨 Graphics & Animation

- **Tile Size**: 32x32 pixels (scaled to 64x64)
- **Screen Resolution**: 768x576 pixels (16x12 tiles visible)
- **Character Sprites**: 8-directional movement with 2-frame animation
- **Smooth Animation**: 60 FPS with sprite counter system
- **Camera System**: Follows player with proper culling for performance

## 🔊 Audio System

The game includes several audio tracks:
- **Theme Music**: Background music
- **Coin Sound**: Collectible pickup sound
- **Powerup Sound**: Power-up effect
- **Unlock Sound**: Door unlocking
- **Fanfare Sound**: Achievement/celebration

## 🎭 Game States

1. **Title State** (0): Main menu (not implemented)
2. **Play State** (1): Normal gameplay
3. **Pause State** (2): Game paused
4. **Dialogue State** (3): NPC conversation

## 🧩 Technical Implementation

### Game Loop
- **Fixed 60 FPS** timing system
- **Delta time** calculation for smooth movement
- **Double buffering** for flicker-free rendering

### Collision Detection
- **Tile-based collision** for world boundaries
- **Object collision** for collectibles and obstacles
- **Entity collision** for NPC interactions
- **Solid area** system for precise collision detection

### Rendering System
- **Camera-relative rendering** for large worlds
- **Culling system** for performance optimization
- **Sprite animation** with frame timing
- **UI overlay** system

## 🚀 How to Run

### Prerequisites
- Java 8 or higher
- IntelliJ IDEA (recommended) or any Java IDE

### Running the Game
1. Open the project in IntelliJ IDEA
2. Navigate to `src/main/Main.java`
3. Run the `main` method
4. The game window will open and start automatically

### Building from Command Line
```bash
# Compile all Java files
javac -d out src/**/*.java

# Run the game
java -cp out main.Main
```

## 🎯 Gameplay Features

### Character Movement
- Smooth 8-directional movement
- Collision detection with world boundaries
- Animated sprite transitions
- Speed-based movement system

### NPC Interaction
- **Vlad NPC**: Random movement pattern
- **Dialogue System**: Multi-line conversations
- **Face Player**: NPCs turn to face the player during dialogue
- **Enter Key**: Trigger conversations

### Object System
- **Collectible Objects**: Keys, boots, chests
- **Collision Objects**: Doors, walls
- **Interaction System**: Player can interact with objects

## 🔧 Development Features

### Debug Tools
- **Draw Time Display**: Press 'T' to show rendering performance
- **Solid Area Visualization**: Collision box debugging (commented out)
- **FPS Counter**: Performance monitoring

### Extensibility
- **Modular Design**: Easy to add new entities, objects, and tiles
- **Resource Management**: Centralized asset loading
- **State System**: Clean game state management

## 📁 Resource Files

### Maps
- `worldV2.txt`: Main world map (50x50 grid)
- Additional map files for different levels

### Sprites
- **Player**: 8-directional movement sprites
- **NPC**: Vlad character sprites
- **Objects**: Key, door, chest, boots
- **Tiles**: Various terrain types (grass, water, road, etc.)

### Audio
- Background music and sound effects in WAV format

### Fonts
- Custom fonts for UI rendering

## 🎨 Customization

### Adding New Objects
1. Create a new class extending `SuperObject`
2. Load appropriate sprite in constructor
3. Add to `AssetSetter.setObject()` method

### Adding New NPCs
1. Create a new class extending `Entity`
2. Implement movement logic in `setAction()`
3. Add dialogue in `setDialogue()`
4. Place in world via `AssetSetter.setNPC()`

### Modifying the World
1. Edit `res/maps/worldV2.txt` with new tile IDs
2. Add new tile types in `TileManager.getTileImage()`
3. Update collision properties as needed

## 🐛 Known Issues

- AssetSetter.setObject() method is empty (no objects currently placed)
- Title state not implemented
- Limited object interaction mechanics
- No save/load system

## 🔮 Future Enhancements

- Inventory system
- More NPCs and dialogue
- Combat mechanics
- Multiple levels/worlds
- Save/load functionality
- More interactive objects
- Particle effects
- Mini-map system

## 📝 License

This project is a learning exercise for 2D game development in Java. Feel free to use and modify for educational purposes.

## 👨‍💻 Development

This game demonstrates fundamental concepts of 2D game development:
- Game loop implementation
- Sprite-based rendering
- Collision detection
- State management
- Resource management
- Audio integration
- User input handling

Perfect for learning Java game development fundamentals!
