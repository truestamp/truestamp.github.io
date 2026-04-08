# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static GitHub Pages landing page for the Truestamp organization (truestamp.github.io). Single self-contained `index.html` with inlined CSS and SVG — no build system, no external dependencies.

## Development

Run `caddy run` and open http://localhost:8080, or open `index.html` directly in a browser.

The `.nojekyll` file disables Jekyll processing on GitHub Pages — do not remove it.

## Deployment

Push to `main` — GitHub Pages serves the site automatically.
