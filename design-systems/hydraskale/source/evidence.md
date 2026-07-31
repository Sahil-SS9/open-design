# HydraSkale Token Contract Evidence

## Source

This design system is derived from the HydraSkale Foundry theme contracts:

- **Token schema:** `contracts/brand-tokens.md` in the HydraSkale Foundry repo
- **Theme tokens:** `themes/kinetic/src/tokens.ts` and `themes/corporate/src/tokens.ts`
- **Schema:** `packages/schema/src/tokens.ts` (ThemeTokensSchema, BrandOverrideSchema)

## Token Mapping

The HydraSkale `ThemeTokens` schema uses its own naming convention:

```typescript
interface BrandTokens {
  colours: {
    primary: string  // teal — brand accent
    accent: string    // burnt orange — secondary accent
    ink: string       // charcoal — primary text
    surface: string   // white — card background
    muted?: string    // subtext
    inverse?: string  // canvas background
  }
  fonts: {
    display: string
    body: string
    mono?: string
  }
  radius?: number
  mood?: string
}
```

This maps to the Open Design shared token schema as follows:

| HydraSkale | Open Design | Layer |
|---|---|---|
| colours.primary | --accent | A1-identity |
| colours.accent | --meta | B-slot (used as secondary accent) |
| colours.ink | --fg | A1-identity |
| colours.surface | --surface | A1-identity |
| colours.inverse | --bg | A1-identity |
| colours.muted | --muted | A1-identity |
| fonts.display | --font-display | A1-identity |
| fonts.body | --font-body | A1-identity |
| fonts.mono | --font-mono | A2 |
| radius | --radius-sm | A1-structure |

## Brand Tokens (from themes/kinetic/src/tokens.ts)

```json
{
  "colours": {
    "primary": "#00C896",
    "accent": "#FF4F00",
    "ink": "#0A0A09",
    "surface": "#F0EBDF",
    "muted": "#D4CBB8",
    "inverse": "#FFFFFF"
  },
  "fonts": {
    "display": "Space Grotesk",
    "body": "Geist",
    "mono": "JetBrains Mono"
  },
  "radius": 4,
  "mood": "bold"
}
```

## Validation

All colour values are valid hex. Required fields (primary, accent, ink, surface, display, body) are present. The radius is 4px (sharp, precise). The mood is "bold".