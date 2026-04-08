# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static GitHub Pages landing page for the Truestamp organization (truestamp.github.io). No build system, no external dependencies.

- `index.html` — the page, with inlined CSS. The logo is a separate SVG loaded with `<img>`.
- `404.html` — GitHub Pages' custom not-found page. It duplicates the index styles and uses root-absolute paths (`/favicon.svg`) because it is served at any missing URL.
- `favicon.svg` — the logo mark, extracted from the same master artwork as the logo with colors hard-coded.

## Development

Run `caddy run` and open http://localhost:8080, or open `index.html` directly in a browser. Caddy serves `404.html` for missing paths, as GitHub Pages does.

The `.nojekyll` file disables Jekyll processing on GitHub Pages — do not remove it.

## Deployment

Push to `main` — GitHub Pages serves the site automatically.
