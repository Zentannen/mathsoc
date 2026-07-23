# UCT Mathematics Society Website

The website of the Mathematics Society at the University of Cape Town, built with [Quarto](https://quarto.org).

Live site: https://zentannen.github.io/mathsoc/

## Local development

Requires [Quarto](https://quarto.org/docs/get-started/).

```bash
quarto preview
```

## Deployment

Pushing to `main` triggers the GitHub Actions workflow in
`.github/workflows/publish.yml`, which renders the site and deploys it to
GitHub Pages automatically.

## Editing

- `_quarto.yml` — site title, navigation, footer
- `*.qmd` — page content
- `theme.scss` — colors, fonts, and component styles
- `files/` — PDFs and other downloadable documents
- `mathsoc-calendar.ics` — the subscribable events calendar (keep in sync
  with `events.qmd`)
