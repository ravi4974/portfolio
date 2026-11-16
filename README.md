# Ravi Shankar — Portfolio

Personal portfolio site for Ravi Shankar, Solution Architect (Zurich).
Single static page, no build step, no framework. Served by GitHub Pages.

## Structure

- `index.html` — the whole site (structure, CSS and the small scroll script inline)
- `.nojekyll` — tells Pages to serve files as-is, skipping Jekyll

## Editing

Everything lives in `index.html`. Content is grounded in
`../resume-creator/profile/profile.yaml` — when the profile changes, update the
matching section here.

Text you will most likely touch:

- `.lede` — the opening statement and the two-paragraph summary
- `.work` articles — one per project, with a `<dl class="figures">` row for metrics
- `.job` articles — the experience timeline
- `.stack-grid` — skills grouped by category, not by logo
- `#contact` — email, phone, LinkedIn, location

## Design notes

Warm paper background, hairline rules, one accent (oxide red), Instrument Serif
for display, IBM Plex Mono for metadata. Sticky identity column on desktop,
horizontal nav strip on mobile. Scroll reveal and nav highlighting use
IntersectionObserver and respect `prefers-reduced-motion`. Print stylesheet drops
the nav and forces black on white.

## Local preview

```bash
cd projects/portfolio
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Push to `main`. GitHub Pages serves the repository root.
