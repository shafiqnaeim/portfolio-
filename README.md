# Portfolio (static site)

**One-page** soft dark portfolio for **Muhammad Shafiq Irfan Bin Mohd Naim** — cards, inline SVG icons, and mesh-style background. No build step: open `index.html` in a browser or host as static files.

## Local preview

1. Open `index.html` in Chrome/Edge/Firefox (double-click, or Live Server in VS Code).
2. Google Fonts (Inter + JetBrains Mono) load when online.

## LinkedIn

Profile link is set in `index.html` under **Profile**. Edit there if your URL changes.

## Publish (GitHub Pages)

See **`DEPLOY_GITHUB_PAGES.md`** in this folder.

## Customize

- **Copy / projects:** edit `index.html` — single **Academic projects** section (`#projects`).
- **Theme:** `assets/css/styles.css` — `:root` colours (`--accent`, `--bg0`, surfaces).
- **Photo:** `assets/img/profile.png` (used in the hero). Replace that file to update your headshot.
- **Résumé:** add `assets/files/Internship_Resume_Shafiq.pdf` (see `assets/files/README.txt`). Use **Open in browser** or Live Server if the embedded preview is blank with `file://`.

## Layout notes

- **Desktop:** full nav in the top bar.
- **Narrow screens (≤860px):** nav becomes a **Menu** dropdown (`<details>` / `<summary>`), no extra JavaScript.

## Files

| File | Role |
|------|------|
| `index.html` | Single-page content + SVG sprite |
| `assets/css/styles.css` | Theme, layout, responsive rules |
| `assets/js/main.js` | Footer year only |

---

*Keep coursework repos private if your university requires it; this public page can stay high-level and point to email for demos.*
