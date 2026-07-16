# 🌊 Knot to MPH Converter

A sleek, real-time conversion tool between **knots** (nautical miles per hour) and **miles per hour (MPH)**. Built with pure HTML, CSS, and JavaScript — no frameworks, no dependencies.

---

## ✨ Features

- **Real-time conversion** — results update instantly as you type
- **Bidirectional** — convert from knots to MPH or MPH to knots
- **Dark theme by default** — easy on the eyes with a modern frosted-glass aesthetic
- **Copy to clipboard** — one-click copy of the result
- **Custom precision** — choose 2, 4, or 6 decimal places
- **Unit info tooltips** — hover over flags to learn more about each unit
- **Random speed generator** — get a random speed for fun
- **Direction toggle** — flip between conversion modes with a single click
- **Formula reference** — always know the conversion math

---

## 🚀 Quick Start

1. Open `index.html` in any modern web browser
2. Enter a numeric value in the input field
3. Select the conversion direction using the toggle buttons:
   - **Knots → MPH**: Convert from nautical miles per hour to miles per hour
   - **MPH → Knots**: Convert from miles per hour to nautical miles per hour
4. The result updates in real-time as you type

---

## 📐 Conversion Formula

| Direction | Formula |
|-----------|---------|
| **Knots → MPH** | `mph = knots × 1.15078` |
| **MPH → Knots** | `knots = mph ÷ 1.15078` |

> **1 knot** = **1.15078 mph**

---

## 🎨 Design Highlights

- **Frosted glass effect** using `backdrop-filter: blur(20px)`
- **Smooth animations** — hover effects, button transitions, and a pulse animation on conversion
- **Responsive layout** — looks great on mobile and desktop
- **Gradient background** — deep navy blue theme
- **Dark mode by default** — no theme toggles needed

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Semantic markup |
| CSS3 | Styling, animations, frosted glass effects |
| Vanilla JavaScript | Real-time conversion logic, DOM manipulation |
| Vite | Development server & build tool (optional) |

---

## 📁 Project Structure

```
knot to mph/
├── index.html      # Main application (HTML + CSS + JS)
├── package.json    # Vite configuration
├── vite.config.js  # Vite server settings
└── README.md       # This file
```

---

## 🎯 Quick Tips

| Action | How |
|--------|-----|
| **Copy result** | Click the clipboard icon next to the result |
| **Get random speed** | Click the "Random Speed" button (shakes briefly!) |
| **Change precision** | Use the dropdown in the input field (2/4/6 decimals) |
| **Flip conversion** | Click the toggle buttons to switch directions |

---

## 📄 License

MIT — feel free to use, modify, and share!

---

Made with ❤️ by [ADD3M](https://github.com/ADD3M)
