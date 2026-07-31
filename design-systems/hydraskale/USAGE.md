# HydraSkale Usage Guide

Design System package guide for Open Design agents and reviewers.

## Read Order

1. Read this file first to understand the package contract.
2. Read `DESIGN.md` for visual intent, constraints, and anti-patterns.
3. Paste `tokens.css` into the first artifact `<style>` block before writing component CSS.
4. Use `components.manifest.json` for the compact component inventory; open `components.html` when exact selectors or states matter.
5. Inspect `preview/` pages when a visual sanity check is useful.

## Design Highlights

- Background: `#F0EBDF` (warm cream canvas)
- Surface: `#FFFFFF` (cards, elevated containers)
- Foreground: `#0A0A09` (deep charcoal text)
- Accent: `#00C896` (bold teal — primary CTAs, links, one hero element per screen)
- Meta: `#FF4F00` (burnt orange — secondary accents, highlights)
- Muted: `#6B6B6B` (subtext, captions)
- Radius: 4px sharp radius across all components
- Mood: bold, high-contrast, precise

## Do

- Preserve the schema token names exactly so cross-brand switching stays reliable.
- Use `--accent` for primary actions, links, focus states, and one clear focal element per screen.
- Use `--meta` (burnt orange) sparingly — secondary actions and highlights only.
- Reuse component groups from `components.manifest.json` before inventing new controls.
- Treat `source/` files as audit evidence for the token contract.
- Reference all tokens via `var(--name)` — never use raw hex outside `:root`.

## Avoid

- Avoid raw hex values outside the copied `:root` token block.
- Avoid using burnt orange (#FF4F00) for primary CTAs — reserve for secondary actions.
- Avoid adding new component recipes that are not represented in `components.html` or `DESIGN.md`.
- Avoid off-palette colors when an existing token can solve the problem.