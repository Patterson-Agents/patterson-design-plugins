---
name: patterson-design
description: Design anything on-brand for Patterson Companies (oral & animal health distribution). Use whenever the user asks for Patterson-branded UI, pages, mocks, decks, components, styling, colors, typography, or brand review. Contains tokens, components, logos, fonts, and framework adapters.
user-invocable: true
---

# patterson-brand

Patterson Companies design-system core: brand tokens, fonts, logos, brand imagery, React component library, guideline specimens, and framework adapters (Tailwind v3/v4, UnoCSS, Theme UI, shadcn/ui). Foundation plugin for all Patterson work.

## What this plugin ships

Everything lives under `${CLAUDE_PLUGIN_ROOT}/ds/`, laid out exactly like the Patterson design-system source tree, so every relative reference inside the files (`../../styles.css`, `../../assets/brand/…`, `../../_ds_bundle.js`) resolves without edits.

## Scaffolding workflow

1. Copy the snapshot into the user's project, preserving the tree:

   ```bash
   cp -R "${CLAUDE_PLUGIN_ROOT}/ds" ./patterson
   ```

   If the project already has a `patterson/` design-system folder from another Patterson plugin, merge instead of duplicating — only add the subfolders that are missing.
2. The working entry point is then `patterson/readme.md`.
3. Edit CONTENT in place; keep the structure, class names, and token usage intact. Never inline raw hex colors — use the CSS variables.
4. Open the entry file in a browser (or a static server) to preview.

## Contents

- `ds/styles.css` + `ds/tokens/` — the CSS custom-property system (link `styles.css` only)
- `ds/theme.json` — canonical machine-readable theme (Theme UI spec shape)
- `ds/components/` — React primitives (Button, IconButton, Badge, Stat, Card, Input, Select, Checkbox, Radio, Switch, Alert, Tabs) as `.jsx` + `.d.ts` + per-component `*.prompt.md` usage guides
- `ds/_ds_bundle.js` — compiled component runtime; exposes `window.PattersonCompaniesDesignSystem_1f7cbe`
- `ds/integrations/` — tailwind.css (v4), tailwind.config.js (v3), uno.config.js, theme-ui.js, shadcn-theme.css + README
- `ds/assets/brand/` — official logo lockups (white/navy/sky/square), wave background, photo band, value-prop art
- `ds/assets/fonts/` — Proxima Nova woff2 (400/700/italic)
- `ds/guidelines/` — browser-openable specimen cards for colors, type, spacing, radii, shadows, logo, voice
- `ds/readme.md` — the full design guide (voice, visual foundations, iconography, provenance)

## How to use it

- **Production code:** pick the adapter in `ds/integrations/` that matches the stack (see its README) — every adapter carries the exact brand hexes. For plain CSS, link `ds/styles.css` and use the variables.
- **React prototypes / static mocks:** load `ds/_ds_bundle.js` after React 18 UMD + Babel standalone; read components from `window.PattersonCompaniesDesignSystem_1f7cbe` .
- **Component API details:** read the sibling `*.prompt.md` next to each component before using it.
- **Logos:** always use the bundled SVGs — never redraw the wave mark. White lockup on navy, navy lockup on white.
- Read `ds/readme.md` in full before large design tasks — it is the authoritative guide.

## Patterson brand quick reference

- **Brand:** Patterson Companies, Inc. — oral (dental) & animal health distribution. Since 1877. Promise: *"Trusted Expertise. Unrivaled Support."*
- **Colors:** Navy `#003767` (primary), Sky `#00A8E1` (accent, hovers, stats). Secondary blue `#147EC2`. Tertiary green `#7BC24D`, teal `#00817D`, purple `#522E91` — data/infographics only, never page chrome. Body gray `#58585B`, light gray `#ECECEC`.
- **Type:** Proxima Nova (licensed; woff2 subset bundled), Figtree as free fallback. Bold navy headlines, tight tracking; cool-gray body at 1.6 leading; big sky-blue stats. UPPERCASE letter-spaced eyebrows.
- **Shape:** Pill buttons (navy, shifts to sky on hover), 10px card radius, soft navy-tinted shadows, 3px sky focus ring.
- **Voice:** Confident, warm, plain-spoken. "We" for Patterson, "you" for the customer. Short declarative sentences. Numbers as proof points. **Never use emoji.**
- **Motion:** Restrained, 120–320ms, no bounces, no infinite loops.

All of this is encoded as CSS custom properties in `ds/tokens/*.css` (linked via `ds/styles.css`). Always style with the `--pat-*`, `--surface-*`, `--space-*`, `--fs-*`, `--shadow-*` variables rather than raw hexes.
