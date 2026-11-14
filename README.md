[README.md](https://github.com/user-attachments/files/34861484/README.md)
# Sort It! — The Waste Sprint

A fast, maximalist waste-sorting browser game built for the exhibition **"Environment & Us: Challenges, Awareness, Sustainability"**.

Trash falls from the top. Tap the right bin (Compost, Recycle or Landfill) before it hits the floor. You have 30 seconds.

## Features

- 30-second rounds with a combo multiplier (up to x5)
- Player name entry before each game
- Live rank while playing
- Final score screen with rank title (Landfill Larry to Planet Hero), items sorted and best streak
- Top 10 leaderboard with gold, silver and bronze rows
- Works on phone, tablet and laptop (tap, keys 1/2/3, or arrow keys)
- Maximalist / brutalist design with light and dark mode support
- Single file, no build step, no dependencies (only Google Fonts)

## Run locally

Open `index.html` in any modern browser. That's it.

## Deploy with GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then **Save**.
5. After a minute, the game is live at `https://<your-username>.github.io/<repo-name>/`.

Put that link in a QR code on your exhibition poster.

## Customize

All code is in `index.html`.

| What | Where |
| --- | --- |
| Round length | `left=30` inside `start()`, and `left/30*100` inside `draw()` |
| Trash items | the `IT` array: `[emoji, name, bin]` where bin is `c`, `r` or `l` |
| Bin names | the `BN` object |
| Rank titles and score limits | inside `end()` |
| Colors | CSS variables at the top (`--lime`, `--pink`, `--cyan`, `--bg`, `--ink`) |

## Leaderboard storage

Scores are saved in the browser's `localStorage` (key `sortit:board`), so they stay on the device being used. A repeated name keeps that player's best score.

To reset the leaderboard, open the browser console on the game page and run:

```js
localStorage.removeItem('sortit:board')
```

For a leaderboard shared across many devices, a small backend (for example Firebase or Supabase) would be needed.

## Tech

Plain HTML, CSS and JavaScript in one file. Fonts: Anton, Archivo Black and Space Mono from Google Fonts.
