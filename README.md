# Discord ID Bypass Tool (Pinokio Launcher)

A 1-click Pinokio launcher for the PromptPirate Discord ID Bypass Tool.

This package is standalone: the web app files are included directly in the launcher root, with no runtime clone required.

## What the app does

- Loads rigged 3D avatars (VRM, FBX, GLB/GLTF)
- Controls head and mouth in real time
- Supports keyboard and gamepad input
- Includes a demo model in `demo-model.zip`

## How to use

1. Open this project in Pinokio.
2. Open `index.html` (Pinokio auto-opens static apps).
3. The bundled demo model (`demo-model.zip`) loads automatically.
4. Optional: click `Choose Custom Model File (optional)` to switch to your own VRM/FBX/GLB/ZIP model.

## Project layout

- `index.html`: Main web app
- `pinokio.json`: Pinokio metadata
- `demo-model.zip`: Bundled demo avatar package loaded automatically
- `logo.png`: App icon

## API documentation

This project has no backend HTTP API. Programmatic usage is through browser automation against the web UI.

### JavaScript (Playwright)

```javascript
const { chromium } = require("playwright");

(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto("http://127.0.0.1:YOUR_PORT");
  // Automate UI interactions here
  await browser.close();
})();
```

### Python (Playwright)

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch()
    page = browser.new_page()
    page.goto("http://127.0.0.1:YOUR_PORT")
    # Automate UI interactions here
    browser.close()
```

### curl

```bash
# Check that the local web UI is reachable
curl -I "http://127.0.0.1:YOUR_PORT"
```
