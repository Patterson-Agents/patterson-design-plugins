---
name: tutorialkit-theme
description: Brand a TutorialKit (Astro interactive-tutorial) project for Patterson Companies, or scaffold a new Patterson-branded TutorialKit starter. Use when the user mentions TutorialKit, interactive tutorials, or hands-on training content in the Patterson brand.
user-invocable: true
---

# patterson-tutorialkit

Patterson theme for TutorialKit (Astro-based interactive tutorials): a runnable starter project with the canonical theme.css, brand logos, and a static theme-preview page.

## What this plugin ships

Everything lives under `${CLAUDE_PLUGIN_ROOT}/ds/`, laid out exactly like the Patterson design-system source tree, so every relative reference inside the files (`../../styles.css`, `../../assets/brand/…`, `../../_ds_bundle.js`) resolves without edits.

## Scaffolding workflow

1. Copy the snapshot into the user's project, preserving the tree:

   ```bash
   cp -R "${CLAUDE_PLUGIN_ROOT}/ds" ./patterson
   ```

   If the project already has a `patterson/` design-system folder from another Patterson plugin, merge instead of duplicating — only add the subfolders that are missing.
2. The working entry point is then `patterson/templates/tutorialkit/README.md`.
3. Edit CONTENT in place; keep the structure, class names, and token usage intact. Never inline raw hex colors — use the CSS variables.
4. Open the entry file in a browser (or a static server) to preview.

## Contents

- `ds/templates/tutorialkit/` — runnable TutorialKit starter (Astro + UnoCSS): `theme.css` (the canonical brand theme), `astro.config.mjs`, `uno.config.ts`, `src/`, `public/` (logo.svg, logo-dark.svg)
- `ds/ui_kits/tutorialkit/index.html` — static preview of the themed TutorialKit shell (renders entirely from `--tk-*` vars)
- `ds/assets/brand/` — logo lockups

## Template notes

- **Theming an existing project:** copy `theme.css` into the project root and `public/logo*.svg`; every color is a `--tk-*` variable TutorialKit reads natively.
- **New project:** copy the whole `ds/templates/tutorialkit/` folder, then `bun install && bun run dev` (or npm equivalents). See its README.
- The preview page links the canonical `theme.css` — never copy values out of it; change the token, and both update.

## Patterson brand quick reference

- **Brand:** Patterson Companies, Inc. — oral (dental) & animal health distribution. Since 1877. Promise: *"Trusted Expertise. Unrivaled Support."*
- **Colors:** Navy `#003767` (primary), Sky `#00A8E1` (accent, hovers, stats). Secondary blue `#147EC2`. Tertiary green `#7BC24D`, teal `#00817D`, purple `#522E91` — data/infographics only, never page chrome. Body gray `#58585B`, light gray `#ECECEC`.
- **Type:** Proxima Nova (licensed; woff2 subset bundled), Figtree as free fallback. Bold navy headlines, tight tracking; cool-gray body at 1.6 leading; big sky-blue stats. UPPERCASE letter-spaced eyebrows.
- **Shape:** Pill buttons (navy, shifts to sky on hover), 10px card radius, soft navy-tinted shadows, 3px sky focus ring.
- **Voice:** Confident, warm, plain-spoken. "We" for Patterson, "you" for the customer. Short declarative sentences. Numbers as proof points. **Never use emoji.**
- **Motion:** Restrained, 120–320ms, no bounces, no infinite loops.

All of this is encoded as CSS custom properties in `ds/tokens/*.css` (linked via `ds/styles.css`). Always style with the `--pat-*`, `--surface-*`, `--space-*`, `--fs-*`, `--shadow-*` variables rather than raw hexes.
