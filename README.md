# Knot to MPH Converter

A sleek, real-time conversion tool between **knots** (nautical miles per hour) and **miles per hour (MPH)**. Built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies, runs directly in any browser.

---

## Features

- **Real-time conversion** — results update instantly as you type
- **Bidirectional** — convert from knots to MPH or MPH to knots
- **Dark theme by default** — modern frosted-glass aesthetic
- **Copy to clipboard** — one-click copy with animated feedback
- **Unit info tooltips** — hover over flags to learn about each unit
- **Random speed generator** — get a random speed for fun
- **Direction toggle** — flip between conversion modes
- **Smooth animations** — button ripples, hover effects, pulse on convert
- **Slow color cycling** — buttons drift through a full RGB spectrum over 9 seconds

---

## Quick Start

1. Open `index.html` in any modern web browser
2. Enter a numeric value in the input field
3. Select the conversion direction using the toggle buttons:
   - **Knots → MPH**: Convert from nautical miles per hour to miles per hour
   - **MPH → Knots**: Convert from miles per hour to nautical miles per hour
4. The result updates in real-time as you type

---

## Conversion Formula

| Direction | Formula |
|-----------|---------|
| **Knots → MPH** | `mph = knots × 1.15078` |
| **MPH → Knots** | `knots = mph ÷ 1.15078` |

> **1 knot** = **1.15078 mph**

---

## Design Highlights

- **Frosted glass effect** using `backdrop-filter: blur(20px)`
- **Smooth animations** — ripple effects on button press, hover transitions, pulse animation on conversion
- **Slow color cycling** — buttons drift through a full RGB spectrum over 9 seconds (not individual 3-second intervals)
- **Responsive layout** — looks great on mobile and desktop
- **Gradient background** — deep navy blue theme
- **Dark mode by default** — no theme toggles needed
- **Animated arrow** — rotates 180° when you flip the conversion direction (only toggles, not on each conversion)

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Semantic markup |
| CSS3 | Styling, animations, frosted glass effects |
| Vanilla JavaScript | Real-time conversion logic, DOM manipulation |

---

## Project Structure

```
knot to mph/
├── index.html      # Main application (HTML + CSS + JS)
├── README.md       # Documentation
└── CLAUDE.md       # Project guidance
```

---

## Quick Tips

| Action | How |
|--------|-----|
| **Copy result** | Click the clipboard icon (confetti celebrates!) |
| **Get random speed** | Click the "Random Speed" button (shakes briefly) |
| **Flip conversion** | Click the toggle buttons (ripple effect!) |
| **Watch the colors shift** | Buttons slowly cycle through the full RGB spectrum over 9 seconds |

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
