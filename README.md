# Ravi Shankar — Portfolio

Personal portfolio site for Ravi Shankar, Solution Architect (Zurich).
Single static page, no build step, no framework, no webfonts, no JavaScript.
Served by GitHub Pages.

## Structure

- `index.html` — the whole site (markup, CSS and print styles inline)
- `assets/portrait.jpg` — 420×404 black-and-white portrait used in the hero
- `assets/portrait-sm.jpg` — 210×202 version for small contexts
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
- Portrait: black-and-white, 1px black frame, right-aligned in the hero's last four columns.
- Print stylesheet drops the nav and forces black on white.

## Portrait provenance

`assets/portrait.jpg` is cropped and graded from the public LinkedIn profile
photo (200×200 source), converted to black and white with contrast lifted.
It is a treated photograph, not a synthesised studio headshot — replace it with
a proper shoot when one exists, keeping the same 420×404 crop.

## Local preview

```bash
cd projects/portfolio
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Push to `main`. GitHub Pages serves the repository root.
