# linktree

Personal link page for **@rfldno** (Victor Tabuni), built with static HTML and CSS: no build step and no JavaScript.
It deploys to GitHub Pages on every push to `master` (see [.github/workflows/static.yml](.github/workflows/static.yml)).

## Design

It uses a sharp "anime title card" style: one white card with ink outlines and a hard offset shadow on a warm paper background, topped by a diagonal-cut dark banner with faint speed lines and the Cipher Studio mark.

- **Fonts** (Google Fonts): Bricolage Grotesque (display), Figtree (body), Pixelify Sans (pixel labels)
- **Tokens** are CSS custom properties at the top of [style.css](style.css) (`--ink`, `--paper`, `--accent`, …)
- **Layout**, from top to bottom:
  1. Banner: Cipher Studio logo, "BUILDER" label and handle
  2. Avatar overlapping the banner's cut, then the tagline
  3. Numbered index of main links: 01 My Site, 02 Projects Hub
  4. "Connect": GitHub and LinkedIn as underlined text links
  5. Footer

## Files

| Path | Purpose |
| --- | --- |
| `index.html` | Page markup |
| `style.css` | All styles and design tokens |
| `assets/avatar.webp` / `.png` | Profile picture (288px; the PNG is the fallback and favicon) |
| `assets/cipher-studio-banner.png` | Cipher Studio logo (black on transparent; inverted to white and cropped in CSS via `.logo`) |

## Common edits

- **Add a main link:** copy one `<a class="row">` block inside `nav.index` and bump its `.num` (03, 04, …).
- **Add a social:** copy one `<a>` inside `.socials`. The row wraps on its own.
- **Change the accent color:** set `--accent` in `style.css` (index numbers and social hover).
- **Arrows** are inline SVG icons (`#i-right`, `#i-diag` at the top of `<body>`), not text characters, so phones don't render them as emoji. Reuse them with `<svg class="icon" aria-hidden="true" viewBox="0 0 24 24"><use href="#i-diag"/></svg>`.
- **Hide the speed lines:** delete the `.speed-lines` div in the banner.
- **Replace an image:** keep images small. Export at about 2× the displayed size and include both a WebP file and a PNG or JPG fallback.

## Preview locally

Open `index.html` in a browser, or run `python -m http.server` and go to http://localhost:8000.
