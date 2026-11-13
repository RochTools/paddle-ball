# Paddle Ball

A fast, two-player paddle game for **one device**. One player sits on each side of the phone, and the first to **5 goals** wins.

It is a Progressive Web App: no build step, no libraries, and it works offline once opened.

## How to play

- **Player 1 (bottom):** drag on the bottom half of the screen, or use the `←` `→` keys.
- **Player 2 (top):** drag on the top half of the screen, or use the `A` `D` keys.
- `Space` pauses. `Enter` starts a game from the menu.
- The ball rests on the serving paddle. The server taps their own half (or presses `↑` / `W`) to launch it. After a goal, the player who conceded serves.
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
| `sounds/` | Optional mp3 sound effects (see below) |
| `icons/` | App icons (standard, maskable, Apple touch, favicon) |

## Sounds (mp3)

Drop your own mp3 files into the `sounds/` folder. Any file that is missing keeps the built-in beep.

| File | Plays when |
| --- | --- |
| `hit.mp3` | the ball touches a paddle |
| `wall.mp3` | the ball hits a side wall |
| `goal.mp3` | a goal is scored |
| `win.mp3` | a player wins the match |

Keep `hit` and `wall` short (under half a second). After adding files, bump `VERSION` in `sw.js` so installed copies pick them up.

## Notes

- The canvas runs at up to 1.5x resolution and quietly drops toward 1x if frames get slow.
- When updating the game, change `VERSION` in `sw.js` so installed copies refresh their cache.
