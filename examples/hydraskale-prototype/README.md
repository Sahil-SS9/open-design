# HydraSkale Prototype

A single-file prototype website built using the HydraSkale design system in Open Design v0.16.1.

## Design System

Uses the `hydraskale` design system from `design-systems/hydraskale/`:
- **Teal** (`#00C896`) — primary/accent
- **Burnt Orange** (`#FF4F00`) — secondary/meta
- **Warm Cream** (`#F0EBDF`) — light background
- **Near-black** (`#0A0A09`) — foreground

## Structure

- `index.html` — standalone HTML file using all HydraSkale tokens via CSS custom properties

## Sections

1. **Hero** — headline + subtitle + primary CTA
2. **Features** — 2×2 grid of feature cards (Compute, Storage, AI, Network)
3. **How It Works** — 3-step numbered process
4. **CTA** — secondary call-to-action on warm cream background

## Validation

This prototype uses the exact token values from the HydraSkale design system package. All CSS custom properties resolve to the declared token values. No raw hex colors are used outside the `:root` block.
