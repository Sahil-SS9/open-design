# HydraSkale Design System

> Category: AI & SaaS
> Bold teal + burnt orange brand with high-contrast, roomy layouts.

## 1. Visual Theme & Atmosphere

HydraSkale is an AI-native SaaS brand built for performance and clarity. The visual language is bold, high-contrast, and precise — teal as the primary interaction signal, burnt orange as the secondary accent, on a warm cream canvas with deep charcoal ink.

- **Visual style:** bold, precise, high-contrast
- **Color stance:** primary (teal), secondary (burnt orange), success, warning, danger
- **Design intent:** Keep outputs recognizable to this bold style while preserving usability and readability.

## 2. Color

- **Primary (Accent):** `#00C896` — Bold teal. Primary CTAs, links, interaction signal.
- **Secondary (Meta):** `#FF4F00` — Burnt orange. Secondary actions, highlights.
- **Ink (FG):** `#0A0A09` — Deep charcoal. Primary text.
- **Surface:** `#FFFFFF` — Card / lifted container background.
- **Canvas (BG):** `#F0EBDF` — Warm cream. Page background.
- **Muted:** `#6B6B6B` — Subtext / captions.
- **Border:** `#D4CBB8` — Subtle separation (muted tint at 30%).

- Use Primary (#00C896) for CTA emphasis — max 2 visible uses per screen.
- Use Canvas (#F0EBDF) for large backgrounds; Surface (#FFFFFF) for cards.
- Keep body copy on Ink (#0A0A09) for legibility.
- Burnt orange (#FF4F00) is reserved for secondary actions and highlights — use sparingly.

## 3. Typography

- **Scale:** desktop-first expressive scale, bold and roomy
- **Families:** display=Space Grotesk, body=Geist, mono=JetBrains Mono
- **Weights:** 300, 400, 500, 600, 700
- **Sizes:** xs=12px, sm=14px, base=16px, lg=18px, xl=24px, 2xl=36px, 3xl=54px, 4xl=76px
- Headings carry the bold, precise personality; body text optimizes for scanability and contrast.
- Display tracking: -0.02em on sizes ≥32px.

## 4. Spacing & Grid

- **Spacing scale:** 4px base grid
- **Section rhythm:** 80px desktop / 48px tablet / 32px phone
- Keep vertical rhythm consistent across sections and components.
- Align columns and modules to a predictable 1200px container grid.

## 5. Layout & Composition

- Prefer clear content blocks with consistent internal padding.
- Keep hierarchy obvious: headline → support text → primary action.
- Use whitespace to separate concerns before adding borders or shadows.
- Container: max 1200px, gutters 36px/24px/16px per breakpoint.

## 6. Components

- **Buttons:** primary action uses `#00C896` (teal); secondary actions stay neutral.
- **Inputs:** strong focus-visible states (teal ring), clear labels, predictable error messaging.
- **Cards/sections:** 4px radius, subtle ring elevation, consistent padding.

## 7. Motion & Interaction

- Use short, purposeful transitions (150–250ms) with stable easing.
- Hover: darken accent by 8%; Active: darken by 14%.
- Ensure hover, focus-visible, active, disabled, and loading states are explicit.

## 8. Voice & Brand

- Tone is bold, precise, and confidence-inspiring — matching the visual language.
- Keep microcopy action-oriented and avoid generic filler language.
- Preserve the brand identity in headlines while keeping UI labels literal and clear.

## 9. Anti-patterns

- Do not introduce off-palette colors when an existing token can solve the problem.
- Do not flatten hierarchy by using the same type size/weight for all text.
- Do not add decorative effects that reduce readability or accessibility.
- Do not mix unrelated visual metaphors in the same interface.
- Do not use burnt orange (#FF4F00) for primary CTAs — reserve for secondary actions only.