# Echoes of Ages - Puzzle Platformer Game

A browser-based puzzle-platformer game built with Phaser 3, themed around "The Changing of Time."

## How to Play

1. **Open the Game**: Simply open `echoes-of-ages.html` in any modern web browser with internet connection.

2. **Game Concept**: Control a character who can switch between three ages, each with unique abilities:
   - **Child (Press 1)**: Fast movement, small size (fits in tight spaces), weak jump
   - **Adult (Press 2)**: Normal speed, high jump, can push heavy crates
   - **Elder (Press 3)**: Slow movement, weak jump, reveals hidden platforms

3. **Controls**:
   - **Movement**: Arrow keys or WASD
   - **Jump**: Up arrow or W
   - **Switch Ages**: Number keys 1, 2, 3

4. **Objective**: Explore the level using different age forms to access different areas:
   - Use the **Child** to fit through the narrow tunnel
   - Use the **Adult** to jump to high ledges and push crates
   - Use the **Elder** to reveal and walk on hidden platforms over pits

5. **Timer**: Complete your exploration within 60 seconds or the level resets!

## Game Features

### Three Unique Ages
- **Child** (Green, Small): 
  - Speed: 250 units/sec
  - Jump: 300 units
  - Special: Can fit through narrow passages
  
- **Adult** (Blue, Medium): 
  - Speed: 180 units/sec
  - Jump: 450 units (highest!)
  - Special: Can push heavy crates

- **Elder** (Grey, Medium): 
  - Speed: 120 units/sec
  - Jump: 250 units
  - Special: Reveals hidden platforms

### Level Design
- **Main Floor**: Starting area with full mobility
- **Narrow Tunnel**: Only accessible as Child due to low ceiling
- **High Ledge**: Requires Adult's superior jump height
- **Hidden Platforms**: Cross the pit as Elder to see invisible platforms
- **Movable Crates**: Adult can push these to create new paths

### Game Mechanics
- **Life Cycle Timer**: 60-second countdown representing a life cycle
- **Auto-Reset**: Level automatically resets when timer hits zero
- **Real-time Age Switching**: Change form instantly to adapt to obstacles
- **Physics-based Movement**: Gravity, collision detection, and momentum

## Technical Details

- **Framework**: Phaser 3.55.2 (loaded via CDN)
- **Physics Engine**: Arcade Physics with gravity
- **Graphics**: Geometric shapes (no external assets required)
- **Single File**: Entire game contained in one HTML file
- **No Dependencies**: Only requires internet connection to load Phaser from CDN

## Browser Compatibility

Works in all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

**Note**: Requires internet connection to load the Phaser 3 library from CDN.

## Code Structure

```javascript
preload()  // Empty - using geometric shapes only
create()   // Initialize game objects, physics, UI
update()   // Handle input, age switching, collision logic
```

### Key Functions
- `switchAge(newAge)`: Changes player form and properties
- `updateTimer()`: Countdown mechanism
- `resetLevel()`: Resets game state when timer expires

## Credits

Created as a prototype demonstrating:
- Time-based game mechanics
- Character state management
- Physics-based puzzle design
- Minimalist visual design

Theme: "The Changing of Time"
