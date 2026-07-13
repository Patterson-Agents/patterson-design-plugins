---
name: docs-site
description: Build Patterson-branded documentation sites and doc pages. Use when the user asks for Patterson docs, a documentation site, developer docs, knowledge base, or help center. Ships a VitePress/Diátaxis-styled React UI kit and a standalone docs page template.
user-invocable: true
---

# patterson-docs

Patterson documentation-site package: a VitePress + Diátaxis styled docs UI kit (sidebar nav, content pages, collections) and a browser-openable docs page template.

## What this plugin ships

Everything lives under `${CLAUDE_PLUGIN_ROOT}/ds/`, laid out exactly like the Patterson design-system source tree, so every relative reference inside the files (`../../styles.css`, `../../assets/brand/…`, `../../_ds_bundle.js`) resolves without edits.

## Scaffolding workflow

1. Copy the snapshot into the user's project, preserving the tree:

   ```bash
   cp -R "${CLAUDE_PLUGIN_ROOT}/ds" ./patterson
   ```

   If the project already has a `patterson/` design-system folder from another Patterson plugin, merge instead of duplicating — only add the subfolders that are missing.
2. The working entry point is then `patterson/ui_kits/patterson-docs/index.html`.
3. Edit CONTENT in place; keep the structure, class names, and token usage intact. Never inline raw hex colors — use the CSS variables.
4. Open the entry file in a browser (or a static server) to preview.

## Contents

- `ds/ui_kits/patterson-docs/` — full docs-site UI kit (React 18 UMD + Babel): `app.jsx`, `pages1/2.jsx`, `collections.jsx`, `data.jsx`
- `ds/templates/patterson-docs/PattersonDocs.dc.html` + `support.js` — standalone docs page template, opens directly in a browser
- plus `ds/styles.css`, `ds/tokens/`, `ds/assets/`, `ds/_ds_bundle.js`

## Template notes

- The UI kit follows **Diátaxis**: organize content as tutorials, how-to guides, reference, and explanation; `data.jsx` holds the nav tree and page registry — edit it first.
- The kit's look mirrors VitePress conventions restyled to Patterson tokens; keep the sidebar/content/aside proportions.
- For a single doc page (not a whole site), use `ds/templates/patterson-docs/PattersonDocs.dc.html` and edit its content in place.

## Patterson brand quick reference

- **Brand:** Patterson Companies, Inc. — oral (dental) & animal health distribution. Since 1877. Promise: *"Trusted Expertise. Unrivaled Support."*
- **Colors:** Navy `#003767` (primary), Sky `#00A8E1` (accent, hovers, stats). Secondary blue `#147EC2`. Tertiary green `#7BC24D`, teal `#00817D`, purple `#522E91` — data/infographics only, never page chrome. Body gray `#58585B`, light gray `#ECECEC`.
- **Type:** Proxima Nova (licensed; woff2 subset bundled), Figtree as free fallback. Bold navy headlines, tight tracking; cool-gray body at 1.6 leading; big sky-blue stats. UPPERCASE letter-spaced eyebrows.
- **Shape:** Pill buttons (navy, shifts to sky on hover), 10px card radius, soft navy-tinted shadows, 3px sky focus ring.
- **Voice:** Confident, warm, plain-spoken. "We" for Patterson, "you" for the customer. Short declarative sentences. Numbers as proof points. **Never use emoji.**
- **Motion:** Restrained, 120–320ms, no bounces, no infinite loops.

All of this is encoded as CSS custom properties in `ds/tokens/*.css` (linked via `ds/styles.css`). Always style with the `--pat-*`, `--surface-*`, `--space-*`, `--fs-*`, `--shadow-*` variables rather than raw hexes.
