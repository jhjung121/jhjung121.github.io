# Academic homepage

Static site. No build step, no dependencies.

## Files
- `index.html` — the whole site (hero + Working Papers + Publications + Teaching)
- `style.css` — styles
- `assets/favicon.svg` — tab icon ("JJ"; green is hard-coded, update if `--accent` changes)
- `assets/Jahui_JUNG_CV.pdf` — CV

## Before publishing
- Set `og:url` in `index.html` `<head>` to the real GitHub Pages URL (currently a placeholder).
- Optional: add an `og:image` (~1200×630) for richer link previews.

## Design
Helvetica family throughout — `"Helvetica Neue", Helvetica, Arial, sans-serif`
(`--font-display` and `--font-serif` both point to this stack; kept as two
variables so a future heading/body split is a one-line change). OS fonts
only, no web font to load. Plain white background. Section headings, the
short accent `.tick` marks, and the full-width `.divider` rules between
sections all share one colour (`--accent`, muted sage green) — that's the
only colour accent on the page besides black/grey text and hover states.

- Top banner: brand (left) → top of page; `Working Papers` → `#working-papers`;
  `Publications` → `#publications`; `Teaching` → `#teaching`; `CV` → the PDF,
  opens in a new tab.
- Hero: name, a `.tick`, the intro paragraph, then `Email →` / `CV (PDF) →`
  links (`.hero-links`). No separate contact block in the footer by design.
- Working Papers and Publications are each their own `<section>`: a bare
  `.section-title` + `.tick`, then `.pub-list` directly under it — no
  `.subsection` wrapper, since each only holds one list, and no index number.
- Teaching still uses `.subsection` for its "Teaching Assistant" label, since
  more subsections (e.g. a second role) could go in the same section later.
- `.pub-list` — each entry gets a hairline top divider; `.pub-title` is the
  paper title (add `class="pub-title ext"` + `target="_blank"` if it links out).
- Optional abstract toggle per entry: a plain `<details class="abstract">`
  with `<summary>Abstract</summary>` + `<p>…</p>` — no JS, the `▸` rotates on
  open via `[open]`. Copy the block from the Sejong paper to add one elsewhere.
- `.ta-list` is the grid (`code | name | Sungkyunkwan University, years`); each
  `.ta-row` uses `subgrid` so all rows share the tracks and left edges line up.
  Stacks to two columns below 640px.

## Type scale (`--fs-*` at the top of `style.css`)
`42` display (hero name, tracked caps) / `27` section titles / `17` body /
`15` secondary (meta, nav, footer) / `13` sub-section labels.

## Edit
Content is populated from the CV; update as needed:
- Intro: name, lead paragraph, Email/CV links — `index.html` `<header class="hero">`
- Working Papers / Publications / Teaching entries — `index.html`
- `--accent` colour, `--bg`, `--maxw` width, `--fs-*` sizes — top of `style.css`
- Replace `assets/Jahui_JUNG_CV.pdf` when the CV changes (keep the filename,
  or update both href's in `index.html`)

## Deploy to GitHub Pages
1. Create a repo named `<your-username>.github.io`
2. Push these files to the `main` branch root
3. Settings → Pages → Source: `main` / `/ (root)`
4. Live at `https://<your-username>.github.io` in ~1 min

For a project repo instead (e.g. `homepage`), enable Pages the same way;
it will serve at `https://<your-username>.github.io/homepage/`.
