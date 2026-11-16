# Ravi Shankar — Portfolio

Personal portfolio site for Ravi Shankar, Solution Architect (Zurich).
Single static page, no build step, no framework, no webfonts, no JavaScript.
Served by GitHub Pages.

## Structure

- `index.html` — the whole site (markup, CSS and print styles inline)
- `.nojekyll` — tells Pages to serve files as-is, skipping Jekyll

## Editing

Everything lives in `index.html`. Content is grounded in
`../resume-creator/profile/profile.yaml` — when the profile changes, update the
matching section here.

Blocks you will most likely touch:

- `.statement` — the claim, the side note and the portrait
- `.entry` articles — one per project: headline, detail, `.figures` ledger, `.stack` line
- `.ledger` rows — the experience timeline, one row per role
- `.cap` columns — capability lists, grouped by kind of work
- `.table` — credentials, education and awards
- `#contact` — email, phone, LinkedIn, location

## Design notes

Swiss / International Typographic Style with a UBS palette.

- Palette: `#000000`, `#FFFFFF`, `#E60000` only. That is the actual UBS brand
  palette (red ≈ Pantone 485 C); nothing else appears on the page.
- Type: one family — Helvetica Neue, falling back to Helvetica, Arial,
  Liberation Sans. No webfont is loaded, so first paint is immediate and the
  grid holds on any device.
- Grid: 12 columns, 24px gutter. Flush left, ragged right, nothing centred.
  Work rows run `index | headline | detail` against a `figures` ledger on the right.
- Rules: 1px hairlines, a 6px masthead rule, 3px red underlines on capability heads.
- No portrait for now — the hero relies on type and empty space.
- Print stylesheet drops the nav and forces black on white.

## Local preview

```bash
cd projects/portfolio
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Push to `main`. GitHub Pages serves the repository root.
