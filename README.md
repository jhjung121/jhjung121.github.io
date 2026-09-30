# Academic homepage

Static site. No build step, no dependencies.

## Files
- `index.html` — the whole site (intro + Research + Teaching)
- `style.css` — styles
- `assets/favicon.svg` — tab icon ("JJ"; green is hard-coded, update if `--accent` changes)
- `assets/Jahui_JUNG_CV.pdf` — CV

## Before publishing
- Set `og:url` in `index.html` `<head>` to the real GitHub Pages URL (currently a placeholder).
- Optional: add an `og:image` (~1200×630) for richer link previews.

## Top banner
Sticky banner: brand name (left) → top of page; `Research` → `#research`;
`Teaching` → `#teaching`; `CV` → `assets/Jahui_JUNG_CV.pdf` (opens the PDF in a new tab).

## Colour rule
Body text is black/grey; green (`--accent`) is reserved for links (nav, email,
in-line author link), section headings, and the rules under them. External links
(CV, the publication DOI) carry a trailing `↗` via `a.ext::after` instead of colour.

## Type scale (`--fs-*` at the top of `style.css`)
`42` display (name) / `24` title (section headings, `--fs-title`) / `17` body / `15`
secondary (meta, nav, footer) / `13` label (`.sub-title`). Name, brand, section
headings and paper/course titles are regular weight (`400`), not bold.

## Structure (in `style.css`)
- `h1` — name, regular weight, black
- `.section-title` + `.section-rule` — regular-weight green heading, thin (1px)
  green rule under it (same `--accent`)
- `.subsection` — grid: small upper-case left label (`.sub-title`) + content column;
  `.subsection + .subsection` gets a faint divider + extra space
- `.pub-title` — regular weight, black; if it links out add `class="pub-title ext"` for the `↗`
- `.ta-list` is the grid (`code | name | Sungkyunkwan University, years`); each
  `.ta-row` uses `subgrid` so all rows share the tracks and left edges line up.
  Last track is `max-content` — one line, never past the section rule. Stacks < 640px.

## Edit
Content is populated from the CV; update as needed:
- Intro: name, email line, and the lead paragraph — `index.html` `<header>`
- Working Papers / Publications / Teaching entries — `index.html`
- `--accent` colour, `--maxw` width, `--fs-*` sizes — top of `style.css`
- Replace `assets/Jahui_JUNG_CV.pdf` when the CV changes (keep the filename, or update the href in the banner too)

## Deploy to GitHub Pages
1. Create a repo named `<your-username>.github.io`
2. Push these files to the `main` branch root
3. Settings → Pages → Source: `main` / `/ (root)`
4. Live at `https://<your-username>.github.io` in ~1 min

For a project repo instead (e.g. `homepage`), enable Pages the same way;
it will serve at `https://<your-username>.github.io/homepage/`.
