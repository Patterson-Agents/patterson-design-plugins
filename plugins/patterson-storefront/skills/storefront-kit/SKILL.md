---
name: storefront-kit
description: Build Patterson e-commerce storefront screens (Patterson Dental / Patterson Veterinary). Use when the user asks for storefront, shop, product, category, cart or e-commerce UI in the Patterson brand. Ships the full storefront shell with a Dental/Vet brand toggle.
user-invocable: true
---

# patterson-storefront

Patterson e-commerce storefront UI kit (pattern library v5.7.2 shell), switchable between Dental and Veterinary brands: utility bar, search, category nav + flyouts, hero, featured products, manufacturers, rewards, footer.

## What this plugin ships

Everything lives under `${CLAUDE_PLUGIN_ROOT}/ds/`, laid out exactly like the Patterson design-system source tree, so every relative reference inside the files (`../../styles.css`, `../../assets/brand/…`, `../../_ds_bundle.js`) resolves without edits.

## Scaffolding workflow

1. Copy the snapshot into the user's project, preserving the tree:

   ```bash
   cp -R "${CLAUDE_PLUGIN_ROOT}/ds" ./patterson
   ```

   If the project already has a `patterson/` design-system folder from another Patterson plugin, merge instead of duplicating — only add the subfolders that are missing.
2. The working entry point is then `patterson/ui_kits/storefront/index.html`.
3. Edit CONTENT in place; keep the structure, class names, and token usage intact. Never inline raw hex colors — use the CSS variables.
4. Open the entry file in a browser (or a static server) to preview.

## Contents

- `ds/ui_kits/storefront/` — `index.html` + `StoreHeader.jsx`, `StoreHome.jsx`, `StoreFooter.jsx`, `brands.js` (Dental/Vet config), `icons.jsx`
- plus `ds/styles.css`, `ds/tokens/`, `ds/assets/`, `ds/_ds_bundle.js`

## Kit notes

- `brands.js` drives the Dental ↔ Veterinary toggle (names, nav categories, accent usage) — extend it rather than hard-coding brand strings.
- Keep the storefront chrome order: utility bar → logo+search row → category nav with flyouts → page content → footer.
- Product cards use the standard Card recipe (10px radius, hairline border, hover lift).

## Patterson brand quick reference

- **Brand:** Patterson Companies, Inc. — oral (dental) & animal health distribution. Since 1877. Promise: *"Trusted Expertise. Unrivaled Support."*
- **Colors:** Navy `#003767` (primary), Sky `#00A8E1` (accent, hovers, stats). Secondary blue `#147EC2`. Tertiary green `#7BC24D`, teal `#00817D`, purple `#522E91` — data/infographics only, never page chrome. Body gray `#58585B`, light gray `#ECECEC`.
- **Type:** Proxima Nova (licensed; woff2 subset bundled), Figtree as free fallback. Bold navy headlines, tight tracking; cool-gray body at 1.6 leading; big sky-blue stats. UPPERCASE letter-spaced eyebrows.
- **Shape:** Pill buttons (navy, shifts to sky on hover), 10px card radius, soft navy-tinted shadows, 3px sky focus ring.
- **Voice:** Confident, warm, plain-spoken. "We" for Patterson, "you" for the customer. Short declarative sentences. Numbers as proof points. **Never use emoji.**
- **Motion:** Restrained, 120–320ms, no bounces, no infinite loops.

All of this is encoded as CSS custom properties in `ds/tokens/*.css` (linked via `ds/styles.css`). Always style with the `--pat-*`, `--surface-*`, `--space-*`, `--fs-*`, `--shadow-*` variables rather than raw hexes.
