# Echoes of Ages - Game Mechanics Documentation

## Visual Layout

```
┌─────────────────────────────────────────────────────────────────┐
│ Age: Adult              Time: 60s                               │
│                                                                 │
│                         Child: Fast, Small, Weak Jump           │
│                         Adult: Normal Speed, High Jump, Push... │
│                         Elder: Slow, Reveals Hidden Platforms   │
│                                                                 │
│                                    ┌────────┐                   │
│                                    │ HIGH   │ <- Adult only     │
│                                    │ LEDGE  │                   │
│                                    └────────┘                   │
│                                                                 │
│  ┌────┐                                                         │
│  │PRE │    [hidden] [hidden]        ┌────┐                     │
│  │PIT │     platforms (Elder)        │POST│                     │
│  └────┘                              │PIT │                     │
│                                      └────┘                     │
│                                                                 │
│ ┌──────────┐                                   ┌──┐  ┌──┐      │
│ │  LEFT    │                                   │▓▓│  │▓▓│      │
│ │ PLATFORM │                                   └──┘  └──┘      │
│ └──────────┘                                  crates (pushable) │
│                    ┌─tunnel─┐ <- Child only                    │
│                    │ ─ ─ ─ ─│                                   │
│ ══════════════════════════════════════════════════════════════  │
│                         FLOOR                                   │
│                                                                 │
│ Controls: Arrow/WASD to move | 1=Child 2=Adult 3=Elder         │
└─────────────────────────────────────────────────────────────────┘
```

## Age Abilities Matrix

| Feature              | Child 🟢 | Adult 🔵 | Elder ⚪ |
|---------------------|---------|---------|---------|
| **Movement Speed**   | 250     | 180     | 120     |
| **Jump Power**       | 300     | 450     | 250     |
| **Size (W×H)**      | 20×20   | 30×40   | 30×35   |
| **Narrow Tunnel**    | ✓ Pass  | ✗ Block | ✗ Block |
| **High Ledge**       | ✗ Can't | ✓ Jump  | ✗ Can't |
| **Push Crates**      | ✗ No    | ✓ Yes   | ✗ No    |
| **See Hidden Plat.** | ✗ No    | ✗ No    | ✓ Yes   |

## Game Progression Flow

```
START (Adult form)
    ↓
Explore as different ages
    ↓
┌─────────────────────────────────────┐
│ 1. Press 1 → Child                  │
│    • Navigate through tunnel        │
│    • Access tight spaces            │
│                                     │
│ 2. Press 2 → Adult                  │
│    • Jump to high ledge             │
│    • Push crates to create paths    │
│                                     │
│ 3. Press 3 → Elder                  │
│    • Hidden platforms appear        │
│    • Cross the pit safely           │
└─────────────────────────────────────┘
    ↓
Timer reaches 0?
    ↓
┌───────┐     ┌──────────────┐
│  YES  │────▶│ RESET LEVEL  │
└───────┘     └──────────────┘
    │
    NO
    │
    ▼
Continue exploring
```

## Physics & Collision System

### Collision Matrix
```
             Floor  Platforms  Crates  HiddenPlat
Player         ✓        ✓        ✓      Elder only
Crates         ✓        ✓        ✓         ✗
```

### Hidden Platform Behavior
- **Child/Adult**: Alpha = 0.3, Collision = OFF
- **Elder**: Alpha = 0.8, Collision = ON

### Crate Pushing
- **Child**: Immovable = true (cannot push)
- **Adult**: Immovable = false, Mass = 5 (can push)
- **Elder**: Immovable = true (cannot push)

## Timer System

```javascript
Initial: 60 seconds
Countdown: -1 per second
Warning: Red text at ≤10 seconds
Reset: When timer = 0
```

## Color Scheme

| Element          | Color Code | RGB           | Visual      |
|-----------------|------------|---------------|-------------|
| Child Player    | 0x00ff00   | (0, 255, 0)   | Green       |
| Adult Player    | 0x0066ff   | (0, 102, 255) | Blue        |
| Elder Player    | 0x888888   | (136, 136, 136)| Grey       |
| Platforms       | 0x4a4a4a   | (74, 74, 74)  | Dark Grey   |
| Crates          | 0xcc6600   | (204, 102, 0) | Brown       |
| Hidden Platform | 0xffffff   | (255, 255, 255)| White      |
| Background      | #1a1a2e    | (26, 26, 46)  | Dark Blue   |

## Input Controls

### Keyboard Mapping
```
Movement:
  ←  or  A  : Move Left
  →  or  D  : Move Right
  ↑  or  W  : Jump (when on ground)

Age Switching:
  1 : Transform to Child
  2 : Transform to Adult
  3 : Transform to Elder
```

## Technical Implementation Notes

### Age Switching Logic
- Instant transformation
- Position preserved
- Velocity maintained
- Hitbox updated immediately
- No cooldown period

### Physics Parameters
- **Gravity**: 800 units/s²
- **World Bounds**: 800×600 pixels
- **Bounce**: 0 (no bouncing)
- **Collision**: Arcade Physics body-to-body

### Performance
- Single scene
- No texture loading
- Geometric shapes only
- 60 FPS target
- Minimal memory footprint

## Testing Checklist

- [ ] Can switch between all three ages
- [ ] Child fits through tunnel
- [ ] Adult can reach high ledge
- [ ] Adult can push crates
- [ ] Elder reveals hidden platforms
- [ ] Elder can cross pit on hidden platforms
- [ ] Timer counts down correctly
- [ ] Level resets at 0 seconds
- [ ] All controls respond properly
- [ ] UI displays correct information
