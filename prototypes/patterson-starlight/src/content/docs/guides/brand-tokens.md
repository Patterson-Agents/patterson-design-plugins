---
title: Brand tokens
description: The Patterson color, type, and shape tokens this starter is built on.
---

The Patterson design system is token-first: you reference semantic variables, never
raw hex values. This starter maps those tokens onto Starlight's theme so the docs
render on-brand automatically.

## Core palette

| Token | Value | Use |
|---|---|---|
| `--pat-navy` | `#003767` | Primary — chrome, strong text, primary buttons |
| `--pat-sky` | `#00A8E1` | Accent — hover, focus ring, links on dark |
| `--pat-blue` | `#147EC2` | Links on light backgrounds (contrast-safe) |
| `--pat-gray` | `#58585B` | Body copy |
| `--pat-ink` | `#1D1D20` | Headings on light |

The full ramp (navy/sky tints, cool grays, and the tertiary green/teal/purple
set) lives in the `patterson-brand` plugin's `ds/tokens/` — copy those files in if
you need the complete palette in content.

## Type

Proxima Nova is the brand face, with **Figtree** as the free fallback and a system
stack beneath it. The scale runs from a fluid display size down to 12px captions;
Starlight's body type is set to the Patterson stack via `--sl-font`.

## Shape and interaction

- **Buttons** are pills (`border-radius: 999px`); primary goes navy, shifting to
  sky on hover — the signature Patterson interaction.
- **Cards and callouts** use a 10px radius.
- **Focus** is a 2px sky ring, offset 2px, on every interactive element.

## Voice

Confident, plain-spoken, "we/you", short declarative sentences, numbers as proof.
Never use emoji — this is a B2B healthcare distribution brand.
