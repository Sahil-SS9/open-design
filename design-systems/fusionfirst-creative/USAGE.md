# FusionFirst Creative — Package Guide

Design System package guide for Open Design agents and reviewers.

## Read Order

1. Read this file first to understand the package contract.
2. Read `DESIGN.md` for visual intent, constraints, and anti-patterns.
3. Paste `tokens.css` into the first artifact `<style>` block before writing component CSS.
4. Use `components.manifest.json` for the compact component inventory; open `components.html` when exact selectors or states matter.
5. Inspect `preview/` pages when a visual sanity check is useful.

## Design Highlights

- Background: `#0A0A0B` — deep dark with blue tint
- Surface: `#18181D` — dark surface
- Foreground: `#F5F5F0` — near-white with warmth
- Accent: `#FF5722` (heat) — molten orange, primary actions
- Palette: Heat orange, fusion yellow, plasma cyan, ember red
- Display: Inter Tight — compressed, technical
- Body: Inter — clean, readable
- Mono: JetBrains Mono — terminal aesthetic

## Do

- Preserve the schema token names exactly so cross-brand switching stays reliable.
- Use `--accent` for primary actions, links, focus states, and one clear focal element.
- Reuse component groups from `components.manifest.json` before inventing new controls.
- Treat `source/` files as audit evidence for the brand backfill.
- This system is opt-in — only use for FusionFirst Creative brand projects.

## Avoid

- Avoid raw hex values outside the copied `:root` token block.
- Avoid redefining Tailwind or design-token values independently of `tokens.css`.
- Avoid claiming original upstream source evidence; this package is based on kensei-staging FusionFirst prototypes.
- Avoid applying this system to non-FusionFirst Creative projects.
- Avoid adding new component recipes that are not represented in `components.html` or `DESIGN.md`.
