# Pin Calendar — Electron App

A beautiful minimal dark-theme calendar desktop app built with Electron.

---

## Folder Structure

```
pin-app/
├── main.js          ← Electron main process (window creation, IPC)
├── preload.js       ← Secure bridge: exposes window controls to renderer
├── package.json     ← Project config + electron-builder settings
├── src/
│   └── index.html   ← Your Pin UI (unchanged, plus Electron wiring)
└── assets/
    └── icon.png     ← App icon (replace with higher-res version)
```

---

## Prerequisites

- **Node.js** v18 or newer — https://nodejs.org
- **npm** v9+

---

## Run in Development

```bash
cd pin-app
npm install
npm start
```

This opens Pin as a native desktop window with the custom titlebar.

---

## Build an .exe (Windows)

```bash
npm install
npm run build:win
```

Output: `dist/Pin Setup 1.0.0.exe` — a full NSIS installer.

Requires: Windows or a Windows build environment.  
On Windows, no extra tools needed. `electron-builder` handles everything.

---

## Build for macOS

```bash
npm install
npm run build:mac
```

Output: `dist/Pin-1.0.0.dmg`

---

## Build for Linux

```bash
npm install
npm run build:linux
```

Output: `dist/Pin-1.0.0.AppImage`

---

## Icon

Replace `assets/icon.png` with a 512×512 PNG for best quality.

For Windows, also add `assets/icon.ico` (256×256 ICO).  
For macOS, also add `assets/icon.icns`.

You can convert PNG → ICO free at: https://convertio.co/png-ico/

---

## What was changed from the prototype

1. **Titlebar dots are functional** — red = close, yellow = minimize, green = maximize
2. **Titlebar is draggable** — drag the top bar to move the window
3. **Font fallback** — uses system fonts if Google Fonts is unavailable (offline)
4. **No frame** — native OS chrome removed; custom titlebar used instead
5. **Window is resizable** with minimum size 900×600
