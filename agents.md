# Agents.md — Knot to MPH Converter Development History

This document summarizes the development history of the Knot to MPH Converter project. It provides context for future sessions when context is reset.

---

## Project Overview

A single-file web application (HTML + CSS + JS) that converts between **knots** (nautical miles per hour) and **miles per hour (MPH)** in real time.

### Core Features

- Real-time bidirectional conversion
- Dark theme with frosted glass aesthetic
- Copy-to-clipboard with animated feedback
- Direction toggle buttons with ripple effects
- Animated arrow indicator (rotates 180° on toggle)
- Pulse animation on conversion
- Slow color cycling on buttons (full RGB spectrum over 9 seconds)
- Responsive design
- Keyboard shortcuts (Ctrl+C to copy, Arrow keys to toggle direction)

### Conversion Formula

- **Knots → MPH**: `mph = knots × 1.15078`
- **MPH → Knots**: `knots = mph ÷ 1.15078`

---

## Architecture

### Single HTML File (`index.html`)

The entire application is contained in one file for simplicity and portability.

**Structure:**
- **HTML**: Semantic markup with labeled input fields, toggle buttons, and result display
- **CSS**: Embedded in `<style>` tags with:
  - Gradient background (deep blue theme)
  - Frosted glass effect on cards using `backdrop-filter: blur(20px)`
  - Smooth transitions and hover effects
  - Responsive design for mobile devices
  - Animated arrow indicator that rotates 180° when the conversion direction is toggled (only on toggle, not on each conversion)
  - Pulse animation on result when converting
  - Ripple effects on button press
- **JavaScript**: Embedded in `<script>` tags with:
  - Real-time conversion on `input` event
  - Direction toggle handling
  - Number formatting with `toLocaleString` for proper comma/thousand separators
  - Clipboard API for copying results
  - Confetti animation system
  - Slow color cycling for interactive buttons (full RGB spectrum over 9 seconds)

---

## Key Technical Details

### Input Handling
- Uses `step="any"` to allow decimal values
- Debounced conversion (300ms delay) to avoid excessive calculations
- Validates user input and clears output on invalid entries
- Handles paste events with validation

### Animation System
- **Pulse animation**: Uses a reflow trick (`void resultValue.offsetWidth`) to reset on each conversion
- **Ripple effects**: Created using `::before` pseudo-elements with expanding circles
- **Color cycling**: `@keyframes hueCycle` rotates hue over 9 seconds
- **Arrow rotation**: Only triggers on toggle, not on conversion

### JavaScript Logic
- `CONVERSION_FACTOR = 1.15078`
- Debounce timer prevents rapid-fire conversions
- Pulse animation state tracking (`pulseAnimationActive`)
- Keyboard shortcuts: Ctrl+C for copy, Arrow keys for direction toggle

---

## Recent Changes

### Latest Updates
- Removed random speed generator button
- Changed theme from blue to black/grey color scheme
- Updated documentation (README and CLAUDE.md)

### Previous Iterations
- Added Google AdSense integration (later removed)
- Added blurred background image from assets folder
- Moved background.jpg to assets/ and encrypted with AES-256-CBC
- Multiple UI/UX improvements and JavaScript logic fixes
- Code structure fixes and documentation updates

---

## File Structure

```
knot to mph/
├── index.html      # Main application (HTML + CSS + JS)
├── README.md       # User-facing documentation
├── CLAUDE.md       # Project guidance for Claude Code
└── agents.md       # This file — development history
```

---

## Common Development Tasks

### Changing the Conversion Factor
Edit the `CONVERSION_FACTOR` constant in the JavaScript:
```javascript
const CONVERSION_FACTOR = 1.15078; // 1 knot = 1.15078 mph
```

### Modifying the UI
The CSS is fully scoped and organized. To change colors, look for:
- Gradient background definitions
- Color tokens like `#1a1a2e`, `#4dabf7`, etc.

### Adding New Features
Since there are no build dependencies, you can add new features directly to the HTML/JS:
- New conversion types
- Additional UI elements
- Custom event handlers
- Local storage for saving conversions

---

## Browser Compatibility

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 55+ | ✅ Full support |
| Firefox | 52+ | ✅ Full support |
| Safari | 11+ | ✅ Full support |
| Edge | 79+ | ✅ Full support |
| Opera | 42+ | ✅ Full support |

---

## Offline Usage

This application works entirely offline. Simply:

1. Save `index.html` to your computer
2. Double-click the file to open it in your browser
3. No internet connection, no server, no installation required

You can also host it on any static file server (GitHub Pages, Netlify, Vercel, etc.) — it will work without a backend.

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| **Result not updating** | Ensure the input field has focus. Try typing a number manually. |
| **Animations not playing** | Try refreshing the page or disabling browser extensions that might block animations. |
| **Clipboard copy doesn't work** | Ensure you have clipboard permissions enabled in your browser. Try clicking the copy icon again. |
| **Random speed button not working** | Check that JavaScript is enabled in your browser. Try a different browser. |
| **Colors not cycling** | This is intentional behavior — the spectrum cycles slowly over 9 seconds. |
| **Input field not accepting decimals** | The `step="any"` attribute allows any numeric input, including decimals. |
| **Confetti not appearing** | Ensure your browser supports the Canvas API and Web Animations API. |

---

## Developer Extension Guide

### Forking and Customizing

This project is intentionally minimal and dependency-free, making it easy to fork and extend:

#### 1. **Modify the Conversion Factor**
```javascript
// In index.html, change the CONVERSION_FACTOR constant
const CONVERSION_FACTOR = 1.15078; // 1 knot = 1.15078 mph
```

#### 2. **Add New Conversion Types**
```javascript
// Add a new conversion function to the conversions object
const conversions = {
  knotsToMph: (knots) => knots * CONVERSION_FACTOR,
  mphToKnots: (mph) => mph / CONVERSION_FACTOR,
  // Add your new conversion here
};
```

#### 3. **Customize Colors**
```css
/* Change the gradient background */
body {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
}

/* Change button colors */
.btn {
  background: linear-gradient(45deg, #4dabf7, #4dabf7);
}
```

#### 4. **Add More Animations**
```css
/* Add a custom animation */
@keyframes custom {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}
```

#### 5. **Add New Features**
Since there are no build dependencies, you can add new features directly to the HTML/JS:
- New conversion types
- Additional UI elements
- Custom event handlers
- Local storage for saving conversions

### Adding a New Conversion Type

1. Add the conversion function to the `conversions` object
2. Update the `toggleConversion` function to include the new type
3. Add the UI elements (buttons, labels) to the HTML
4. Update the `CONVERSION_FACTOR` if needed

### Testing Your Changes

1. Save your changes to `index.html`
2. Open the file in a browser
3. Test the new functionality
4. Check for console errors using F12 → Console

---

## License

MIT — feel free to use, modify, and share!

---

Made with ❤️ by [ADD3M](https://github.com/ADD3M)
