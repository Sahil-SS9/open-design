# FusionFirst Creative — Source Evidence

## Source Location

```
/home/kensei/kensei-staging/fusionfirststudios-site/prototype/
```

## Files Referenced

- `styles.css` — primary stylesheet containing the :root token block
- `index.html` — HTML structure with component examples

## Token Mapping

All tokens in `tokens.css` were derived from the creative prototype's `styles.css` :root block. The original source uses these token names directly; this package maps them to Open Design's shared schema.

## Design Decisions

- `--bg: #0A0A0B` — pure dark with slight blue tint, matches creative prototype
- `--surface: #18181D` — dark surface with subtle texture
- `--accent: #FF5722` — heat (molten orange), the primary brand color
- `--fg: #F5F5F0` — near-white with slight warmth
- `--font-display: 'Inter Tight'` — compressed, bold, technical display font
- `--font-body: 'Inter'` — clean body font
- `--font-mono: 'JetBrains Mono'` — terminal-style monospace

## Verification

Token values were verified against the source stylesheet. Line numbers in `token-contract.report.json` reference the `tokens.css` file in this package.
