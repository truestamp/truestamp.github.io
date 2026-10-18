# AGENTS.md

Static GitHub Pages landing page for the Truestamp organization (https://truestamp.github.io/). No build system, no external dependencies.

- `index.html` — the page, with inlined CSS. The logo is a separate SVG loaded with `<img>`.
- `404.html` — the custom not-found page GitHub Pages serves at any missing path.
- `favicon.svg` — the logo mark, extracted from the same master artwork as the logo.

## Conventions

- `404.html` uses the same `<style>` block as `index.html`, word for word; copy it across after changing either. It also needs root-absolute paths (`/favicon.svg`).
- Colors and type follow www.truestamp.com: slate `#1e2225` background, `#e0e5e9` text, `#9aa4ad` secondary text, `#468fee` links, Inter with system fallbacks.
- Size text in `rem`, never `vw`, so it still reaches 200% under browser zoom.
- The logo and favicon are copyrighted brand artwork. Regenerate them from the master logo SVG rather than editing them by hand.
- Check both pages with an accessibility checker such as axe-core after changing markup or styles.

## Development

Run `caddy run` and open http://localhost:8080; it serves `404.html` for missing paths, as GitHub Pages does. In the Claude desktop app, `.claude/launch.json` starts the same server in the preview pane.

Don't remove `.nojekyll`; it turns off Jekyll processing on GitHub Pages.

## Deployment

Push to `main` and GitHub Pages publishes the repository root. Pages caches responses for up to 10 minutes, so a fresh deploy may not show immediately.
