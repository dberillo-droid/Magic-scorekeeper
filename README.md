# Magic Score 🧙‍♂️

PWA scorekeeper for **Magic: The Gathering**, mobile-first.
No installation required — runs straight from the browser and can be added to the Home screen as a native app.

🔗 **Live**: https://dberillo-droid.github.io/Magic-scorekeeper/

---

## Features

### 🃏 Player management
- **2 to 6 players** simultaneously
- Configurable starting life: **20 / 30 / 40 / 60 LP**
- **Poison** counter (☠ 0–10) and **energy** counter (⚡ 0–5)
- Mana color and icon auto-assigned based on the chosen type (White, Blue, Black, Red, Green, Colorless)
- Custom background image per player
- Adaptive layout: vertical on phones, grid on tablet / desktop

### 🎲 3D Dice (WebGL)
- Support for **D2, D4, D6, D10, D20**
- Each die is a real 3D mesh rendered with WebGL — proper geometry, planar faces, matcap "liquid metal" shading:
  - **D2**: animated coin flip
  - **D4**: regular tetrahedron, 4 triangular faces
  - **D6**: chamfered cube with bevelled edges and dot pips
  - **D10**: pentagonal trapezohedron, digits 1–9 + "0" for 10
  - **D20**: icosahedron, 20 triangular faces with digits 1–20
- The face that lands always faces the camera squarely — no overlapping side faces
- Per-roll **rolling sound** that follows the easing curve (denser clicks at start, sparser as the die slows down). Lower-pitched for bigger dice.
- **Result highlight**: green glow for the best roll, red glow for the worst
- Final-result audio: ascending fanfare for the max roll, descending tones for `1` (fumble), settle thud otherwise

### ↩ Undo
- Undo the last **life points** or **poison** change
- History keeps the last 40 actions

### 🏆 Winner detection
- Automatic banner when a single player is still alive
- Disappears automatically when you start a new game

### 🔍 Card search
- Search any MTG card by name
- Multiple-result picker, exact match opens straight to detail
- Shows: **oracle text** (official rules), Wizards of the Coast **rulings**, direct **Gatherer** link
- Italian / English language toggle to fetch the appropriate printing
- Powered by [Scryfall API](https://scryfall.com)

### 💾 Session persistence
- Player names, life, counters and background images are **saved automatically**
- State is restored exactly as you left it on next launch

---

## Install as an app (PWA)

### iPhone / iPad
1. Open the URL in **Safari**
2. Tap **Share** → **Add to Home Screen**

### Android
1. Open the URL in **Chrome**
2. Tap the **⋮** menu → **Add to Home Screen**

---

## Local development

The project is a single `index.html` file — no dependencies, no build step.

```bash
git clone https://github.com/dberillo-droid/Magic-scorekeeper
cd Magic-scorekeeper
# Start a local server (e.g. Python)
python -m http.server 3333
# or with Node
npx serve .
```

Then open `http://localhost:3333` in your browser.

---

## Tech stack

- Vanilla HTML / CSS / JavaScript — no framework
- WebGL 1 for the 3D dice (custom matcap shader, planar polyhedra, digit atlas)
- Web Audio API for synthesised dice / coin / UI sounds
- [Scryfall API](https://scryfall.com/docs/api) for card data
- PWA with Service Worker
- `localStorage` for session persistence

---

## License

MIT
