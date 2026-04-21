# Build Instructions — Flappy Mauri

## Prerequisites
- A modern web browser (Chrome 90+, Firefox 88+, Safari 14+)
- No build tools, package managers, or servers required

## Build Steps

### 1. Verify asset files are present
```
aws-kiro-workshop/
├── index.html
└── assets/
    ├── ghosty.png
    ├── jump.wav
    └── game_over.wav
```

### 2. Open the game
Double-click `index.html` — it opens directly in your default browser.

> **Note**: Some browsers block `file://` Audio autoplay. If sounds don't play on first load, click anywhere on the canvas once to unlock the audio context (browser security policy). Alternatively, serve via a local server (see below).

### Optional: Local server (resolves audio autoplay restrictions)
```bash
# Python 3
python3 -m http.server 8080
# then open http://localhost:8080

# Node.js (npx, no install needed)
npx serve .
# then open the URL shown
```

## Build Artifacts
- `index.html` — the complete game (single file, no compilation needed)
