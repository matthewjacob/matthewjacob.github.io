# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About This Site

Matthew Jacob's personal academic website (PhD Candidate, Harvard). Built on the Minimal Mistakes Jekyll theme (v4.27.2), hosted on GitHub Pages.

## Build & Development Commands

```bash
# Install dependencies
bundle install

# Run local development server at http://localhost:4000/test/
bundle exec rake preview

# Minify JavaScript (after editing assets/js/_main.js)
bundle exec rake js
```

JavaScript is authored in `assets/js/_main.js` and built to `assets/js/main.min.js`. Run `rake js` after any JS changes.

## Architecture

The site is a standard Jekyll installation with minimal customization on top of the Minimal Mistakes theme:

- **Content lives in `_pages/`** — `index.md` (homepage) and `research.md` are the only real content files
- **Site config is `_config.yml`** — author info, social links, analytics, theme skin (`air`)
- **Navigation is `_data/navigation.yml`** — Home, Research, CV links
- **Custom styles are in `assets/css/main.scss`** — this imports the theme, then adds overrides (larger author avatar at 200px, section header borders via `.section-header`, sidebar opacity fix, hidden permalink anchors)
- **`_layouts/`, `_includes/`, `_sass/`** — Minimal Mistakes theme files; avoid modifying unless necessary

The `docs/` and `test/` directories contain theme demo/test content and are not part of the live site.

## Deployment

Pushing to `master` triggers GitHub Actions (`.github/workflows/build.yml`), which bundles dependencies and updates the Algolia search index. GitHub Pages handles the actual Jekyll build and deployment automatically.
