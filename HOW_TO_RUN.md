# How to Run Echoes of Ages

## Quick Start

1. **Download the file**: Get `echoes-of-ages.html` from this repository
2. **Open in browser**: Double-click the file or drag it into any modern web browser
3. **Ensure internet connection**: The game needs to load Phaser 3 library from CDN
4. **Start playing**: The game loads automatically!

## System Requirements

- **Browser**: Any modern browser (Chrome, Firefox, Safari, Edge)
- **Internet**: Required for initial Phaser 3 library load
- **JavaScript**: Must be enabled

## No Installation Required

This is a self-contained HTML file with:
- ✅ No dependencies to install
- ✅ No build process needed
- ✅ No server required
- ✅ Works offline after initial library load

## Game Controls

```
Movement:
  ← → ↑ ↓  (Arrow keys)
  or
  A D W S  (WASD keys)

Age Switching:
  1 - Transform to Child (Fast, Small, Weak Jump)
  2 - Transform to Adult (Strong Jump, Push Crates)  
  3 - Transform to Elder (Reveal Hidden Platforms)
```

## Troubleshooting

### Game doesn't load?
- Check internet connection (needed for Phaser CDN)
- Try a different browser
- Ensure JavaScript is enabled
- Check browser console for errors (F12)

### Performance issues?
- Close other tabs/applications
- Try a different browser
- The game is optimized and should run at 60 FPS on most systems

### Controls not working?
- Click on the game canvas to focus it
- Ensure NumLock is on for number keys
- Try both arrow keys and WASD

## File Structure

```
echoes-of-ages.html (Single file contains everything)
├── HTML structure
├── CSS styling
└── JavaScript game logic
    ├── Game configuration
    ├── Phaser scene (preload, create, update)
    ├── Player mechanics
    ├── Physics system
    └── UI elements
```

## Features Implemented

✅ Three age system with unique abilities
✅ Smooth physics-based movement
✅ Multiple challenge areas (tunnel, ledge, pit)
✅ Hidden platforms mechanic
✅ Pushable crates
✅ 60-second countdown timer
✅ Auto-reset on timeout
✅ Comprehensive UI display

## Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome  | 90+     | ✅ Fully Supported |
| Firefox | 88+     | ✅ Fully Supported |
| Safari  | 14+     | ✅ Fully Supported |
| Edge    | 90+     | ✅ Fully Supported |
| Opera   | 76+     | ✅ Fully Supported |

## Development Notes

- Built with Phaser 3.55.2
- Uses Arcade Physics engine
- Geometric shapes (no image assets)
- Single HTML file for easy distribution
- Optimized update loop
- Clean, maintainable code structure

## Support

If you encounter any issues:
1. Check the browser console (F12 → Console tab)
2. Verify internet connection for CDN access
3. Try a different browser
4. Ensure you're using the latest version of the file

## Have Fun!

Experiment with different age forms to discover how to navigate the entire level. Remember, you have 60 seconds before the timer resets everything!
