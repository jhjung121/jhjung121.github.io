# Academic homepage

Static site. No build step, no dependencies.

## Files
- `index.html` — the whole site (intro + Research + Teaching)
- `style.css` — styles
- `assets/favicon.svg` — tab icon ("JJ"; green is hard-coded, update if `--accent` changes)
- `assets/cv.pdf` — CV (add your own)

## Before publishing
- Set `og:url` in `index.html` `<head>` to the real GitHub Pages URL (currently a placeholder).
- Optional: add an `og:image` (~1200×630) for richer link previews.

## Top banner
Sticky banner: brand name (left) → top of page; `Research` → `#research`;
`Teaching` → `#teaching`; `CV` → `assets/cv.pdf` (opens the PDF in a new tab).

## Colour rule
Text is black/grey; green (`--accent`) is reserved for links (nav, email,
in-line author link) and the rules under section headings. External links
(CV, the publication DOI) carry a trailing `↗` via `a.ext::after` instead of colour.

## Type scale (`--fs-*` at the top of `style.css`)
`42` display (name) / `30` title (section headings) / `17` body / `15` secondary
(meta, nav, footer) / `13` label (`.sub-title`). Bold is always `700`.

## Structure (in `style.css`)
- `h1` — name (black)
- `.section-title` + `.section-rule` — black heading, long thin green rule under it
- `.subsection` — grid: small upper-case left label (`.sub-title`) + content column;
  `.subsection + .subsection` gets a faint divider + extra space
- `.pub-title` — black; if it links out add `class="pub-title ext"` for the `↗`
- `.ta-list` is the grid (`code | name | Sungkyunkwan University, years`); each
  `.ta-row` uses `subgrid` so all rows share the tracks and left edges line up.
  Last track is `max-content` — one line, never past the section rule. Stacks < 640px.

## Edit
Content is populated from the CV; update as needed:
- Intro: name, email line, and the lead paragraph — `index.html` `<header>`
- Working Papers / Publications / Teaching entries — `index.html`
- `--accent` colour, `--maxw` width, `--fs-*` sizes — top of `style.css`
- Replace `assets/cv.pdf` when the CV changes

## Deploy to GitHub Pages
1. Create a repo named `<your-username>.github.io`
2. Push these files to the `main` branch root
3. Settings → Pages → Source: `main` / `/ (root)`
4. Live at `https://<your-username>.github.io` in ~1 min

For a project repo instead (e.g. `homepage`), enable Pages the same way;
it will serve at `https://<your-username>.github.io/homepage/`.
