# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A simple two-way conversion website between **knots** (nautical miles per hour) and **miles per hour (MPH)**, built as a single HTML file with embedded CSS and JavaScript. No frameworks or build steps required.

## Quick Start

1. Open `index.html` in a web browser
2. Enter a numeric value in the input field
3. Select the conversion direction using the toggle buttons:
   - **Knots → MPH**: Convert from nautical miles per hour to miles per hour
   - **MPH → Knots**: Convert from miles per hour to nautical miles per hour
4. The result updates in real-time as you type

## Conversion Formula

- **Knots to MPH**: `mph = knots × 1.15078`
- **MPH to Knots**: `knots = mph ÷ 1.15078`

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

## File Structure

```
knot to mph/
├── index.html  # Main application (HTML + CSS + JS)
├── README.md   # Documentation
└── CLAUDE.md   # This file
```

## Common Development Tasks

### Changing the Conversion Factor
Edit the `CONVERSION_FACTOR` constant in the JavaScript:
```javascript
const CONVERSION_FACTOR = 1.15078; // 1 knot = 1.15078 mph
```

### Modifying the UI
The CSS is fully scoped and organized. To change colors, look for the gradient definitions and color tokens like `#1a1a2e`, `#4dabf7`, etc.

### Adding New Features
Since there are no build dependencies, you can add new features directly to the HTML/JS without worrying about bundling or transpilation.

## Notes

- The `step="any"` attribute on inputs allows decimal values
- Zero and negative values are accepted
- The result is displayed with 2 decimal places by default, formatted with commas for thousands
- The pulse animation uses a reflow trick (`void resultValue.offsetWidth`) to reset the animation on each conversion
- Confetti is fired on copy, direction toggle, and random speed generation
- Buttons slowly cycle through a full RGB spectrum over 9 seconds (not individual 3-second intervals)
- The animated arrow rotates 180° only when the conversion direction is toggled (not on each conversion)
