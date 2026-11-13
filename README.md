# Paddle Ball

A fast, two-player paddle game for **one device**. One player sits on each side of the phone, and the first to **5 goals** wins.

It is a Progressive Web App: no build step, no libraries, and it works offline once opened.

## How to play

- **Player 1 (bottom):** drag on the bottom half of the screen, or use the `←` `→` keys.
- **Player 2 (top):** drag on the top half of the screen, or use the `A` `D` keys.
- `Space` pauses. `Enter` starts a game from the menu.
- Each hit makes the ball a little faster, and hitting it with the paddle's edge changes the angle.

## Run it

Open `index.html` in a browser to play. To use the install and offline features, serve the folder over HTTPS, or over `localhost` for testing:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Install as an app

- **Android / Chrome / Edge:** tap **Install app** on the menu, or use the browser's install option.
- **iPhone (Safari):** tap **Share**, then **Add to Home Screen**.

## Deploy with GitHub Pages

1. Push these files to a repository.
2. Go to **Settings → Pages**, choose your branch and the `/ (root)` folder, then save.
3. Open the URL GitHub gives you.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole game (HTML, CSS and JavaScript) |
| `manifest.webmanifest` | App name, icons, fullscreen and portrait settings |
| `sw.js` | Service worker: caches the files so the game works offline |
| `icons/` | App icons (standard, maskable, Apple touch, favicon) |

## Notes

- The canvas runs at up to 1.5x resolution and quietly drops toward 1x if frames get slow.
- When updating the game, change `VERSION` in `sw.js` so installed copies refresh their cache.
