# linktree

Personal link page for **@rfldno** (Victor Tabuni), built with static HTML and CSS: no build step and no JavaScript.
It deploys to GitHub Pages on every push to `master` (see [.github/workflows/static.yml](.github/workflows/static.yml)).

## Design

It uses a retro "character sheet" style with a warm paper background, ink outlines, hard offset shadows and a pixel font for game-style labels.

- **Fonts** (Google Fonts): Bricolage Grotesque (display), Figtree (body), Pixelify Sans (pixel labels)
- **Tokens** are CSS custom properties at the top of [style.css](style.css) (`--ink`, `--paper`, `--accent`, …)
- **Layout**, from top to bottom:
  1. Profile header: avatar, handle and tagline
  2. Level meter: 10 pips
  3. Featured "My Site" card with a portfolio screenshot
  4. "Side Quests" grid: GitHub and LinkedIn
  5. Footer

## Files

| Path | Purpose |
| --- | --- |
| `index.html` | Page markup |
| `style.css` | All styles and design tokens |
| `assets/avatar.webp` / `.png` | Profile picture (288px; the PNG is the fallback and favicon) |
| `assets/site-preview.webp` / `.jpg` | Portfolio screenshot for the featured card (1100px wide) |

## Common edits

- **Change the level:** in `index.html`, set how many `.pip` elements have the `on` class, then update the `LEVEL n/10` text, the `XP to n+1 →` text and `aria-valuenow`. At level 10, change the XP text to `MAX`.
- **Change the accent color:** set `--accent` in `style.css`. The design's alternates are `#6f8f5a` (green) and `#4f7bd9` (blue).
- **Add a side quest:** copy one `<a class="quest">` block inside `.quest-grid`. The grid wraps on its own.
- **Replace an image:** keep images small. Export at about 2× the displayed size and include both a WebP file and a PNG or JPG fallback.

## Preview locally

Open `index.html` in a browser, or run `python -m http.server` and go to http://localhost:8000.
