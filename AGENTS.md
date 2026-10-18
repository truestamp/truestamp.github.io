# AGENTS.md

Guidance for coding agents working in this repository.

## Overview

Static GitHub Pages landing page for the Truestamp organization (https://truestamp.github.io/). No build system, no external dependencies.

- `index.html` — the page, with inlined CSS. The logo is a separate SVG loaded with `<img>`.
- `404.html` — GitHub Pages' custom not-found page, served at any missing URL.
- `favicon.svg` — the logo mark, extracted from the same master artwork as the logo, with colors hard-coded.
- `CLAUDE.md` — only imports this file, for Claude Code setups that don't read `AGENTS.md` directly. Put instructions here, not there.

## Conventions

- `404.html` duplicates the `<style>` block from `index.html`. Keep the two in sync.
- `404.html` must use root-absolute paths (`/favicon.svg`), because it is served from any path.
- Size text in `rem`, never `vw`. Viewport units stop text from reaching 200% under browser zoom (WCAG 1.4.4).
- The logo and favicon are copyrighted brand artwork. Don't hand-edit their paths or colors; regenerate them from the master logo SVG.
- After changing markup or styles, check both pages with an accessibility checker such as axe-core. Both currently have no violations.

## Development

Run `caddy run` and open http://localhost:8080. Caddy serves `404.html` for missing paths, as GitHub Pages does. `index.html` also works opened directly from disk; `404.html` doesn't, because of its root-absolute paths.

The `.nojekyll` file disables Jekyll processing on GitHub Pages — do not remove it.

## Deployment

Push to `main` and GitHub Pages publishes the site from the repository root. Responses are cached for up to 10 minutes (`Cache-Control: max-age=600`), so a fresh deploy may not show immediately.
