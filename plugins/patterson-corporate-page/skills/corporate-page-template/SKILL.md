---
name: corporate-page-template
description: Build a Patterson-branded web page (marketing, landing, informational). Use when the user asks for a Patterson web page, landing page, or site section. Scaffolds a React shell with sticky nav, navy hero, content band, and footer wired to brand tokens and components.
user-invocable: true
---

# patterson-corporate-page

Patterson corporate web page shell: sticky nav with logo, navy hero, content band, and footer — a React starting point for any on-brand marketing or informational page.

## What this plugin ships

Everything lives under `${CLAUDE_PLUGIN_ROOT}/ds/`, laid out exactly like the Patterson design-system source tree, so every relative reference inside the files (`../../styles.css`, `../../assets/brand/…`, `../../_ds_bundle.js`) resolves without edits.

## Scaffolding workflow

1. Copy the snapshot into the user's project, preserving the tree:

   ```bash
   cp -R "${CLAUDE_PLUGIN_ROOT}/ds" ./patterson
   ```

   If the project already has a `patterson/` design-system folder from another Patterson plugin, merge instead of duplicating — only add the subfolders that are missing.
2. The working entry point is then `patterson/templates/corporate-page/index.html`.
3. Edit CONTENT in place; keep the structure, class names, and token usage intact. Never inline raw hex colors — use the CSS variables.
4. Open the entry file in a browser (or a static server) to preview.

## Contents

- `ds/templates/corporate-page/index.html` — page shell (React 18 UMD + Babel, in-browser JSX)
- `ds/templates/corporate-page/ds-base.js` — loads tokens + `_ds_bundle.js` (base path `../..`)
- plus `ds/styles.css`, `ds/tokens/`, `ds/assets/`, `ds/_ds_bundle.js`

## Template notes

- No build step: React + Babel standalone run in the browser; JSX lives inline in `index.html`.
- Design-system components come from `window.PattersonCompaniesDesignSystem_1f7cbe` (Button, Card, Stat, Badge, …) once `_ds_bundle.js` loads.
- Add sections inside the `<main>` between hero and footer; use `pat-container` for the centered max-width column and `--space-*` rhythm (64–128px between sections).

## Patterson brand quick reference

- **Brand:** Patterson Companies, Inc. — oral (dental) & animal health distribution. Since 1877. Promise: *"Trusted Expertise. Unrivaled Support."*
- **Colors:** Navy `#003767` (primary), Sky `#00A8E1` (accent, hovers, stats). Secondary blue `#147EC2`. Tertiary green `#7BC24D`, teal `#00817D`, purple `#522E91` — data/infographics only, never page chrome. Body gray `#58585B`, light gray `#ECECEC`.
- **Type:** Proxima Nova (licensed; woff2 subset bundled), Figtree as free fallback. Bold navy headlines, tight tracking; cool-gray body at 1.6 leading; big sky-blue stats. UPPERCASE letter-spaced eyebrows.
- **Shape:** Pill buttons (navy, shifts to sky on hover), 10px card radius, soft navy-tinted shadows, 3px sky focus ring.
- **Voice:** Confident, warm, plain-spoken. "We" for Patterson, "you" for the customer. Short declarative sentences. Numbers as proof points. **Never use emoji.**
- **Motion:** Restrained, 120–320ms, no bounces, no infinite loops.

All of this is encoded as CSS custom properties in `ds/tokens/*.css` (linked via `ds/styles.css`). Always style with the `--pat-*`, `--surface-*`, `--space-*`, `--fs-*`, `--shadow-*` variables rather than raw hexes.
