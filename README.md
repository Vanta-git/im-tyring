# Vanta Browser (Split Structure)

This is the original Vanta proxy, restructured like Breeze/SVG style:

- Clean `index.html` (no inlined CSS/JS)
- All styles in `assets/css/main.css`
- Main application logic in `assets/js/app.js`
- Scramjet/Vanta runtime stays in `vanta/`

## Structure

```
├── index.html          # Clean entry point
├── assets/
│   ├── css/main.css    # All extracted styles
│   └── js/app.js       # Main browser UI + proxy logic
├── vanta/              # Scramjet-based proxy engine
│   ├── vanta.core.js
│   ├── vanta.api.js
│   ├── vanta.utils.js
│   ├── vanta.sw.js
│   ├── vanta.inject.js
│   └── vanta.wasm
├── sw.js               # Service worker bootstrap
├── sw2.js              # Alternate SW (CDN controller)
└── ...
```

## How to use

Serve the whole folder with any static server (or your existing deploy).
The proxy still uses the same WISP endpoints defined inside `assets/js/app.js`.
