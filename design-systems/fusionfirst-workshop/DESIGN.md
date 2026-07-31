# FusionFirst Workshop — Visual Design Specification

## Visual Theme

Warm dark + amber monochrome. Earthy, grounded, premium.

## Color

- **Background:** `#0A0807` — deep warm black
- **Surface:** `#16120E` — warm dark charcoal
- **Foreground:** `#F2EDE3` — warm cream
- **Accent:** `#E8A04A` — amber
- **Signal green:** `#5EBA82` for success/positive
- **Signal red:** `#EB5757` for errors/negative
- **Signal blue:** `#6F8FE8` for informational

## Typography

- **Display:** Space Grotesk — bold, geometric, warm
- **Body:** Inter — clean, readable, neutral
- **Mono:** JetBrains Mono — for code and technical content
- Scale: 12px → 76px with 1.6 body leading

## Spacing

- 4px base unit, powers of 2: 4, 8, 12, 16, 24, 32, 64, 96, 128
- Section vertical: 96px desktop, 64px tablet, 32px phone
- Container max: 1200px, gutters: 36/24/16

## Layout

- Grid-based with generous whitespace
- Card-based content sections with ring elevation
- Single-column focus on mobile, multi-column on desktop

## Components

- Buttons: primary (amber fill), secondary (surface outline)
- Cards: flat by default, raised with shadow on emphasis
- Badges: solid fill with semantic colors
- Inputs: ring-focused, amber accent on focus
- Keyboard shortcuts: mono styling with ring shadow

## Motion

- Fast: 150ms, Base: 200ms
- Easing: cubic-bezier(0.16, 1, 0.3, 1) — natural spring

## Anti-patterns

- Don't use bright neon colors
- Don't use pure black backgrounds
- Don't mix serif and sans-serif in the same block
