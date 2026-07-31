# FusionFirst Workshop — Source Evidence

## Source Location

```
/home/kensei/kensei-staging/fusionfirststudios-site/prototype-r/workshop/
```

## Files Referenced

- `styles.css` — primary stylesheet containing the :root token block
- `index.html` — HTML structure with component examples
- `script.js` — interactive behavior (not token-relevant)

## Token Mapping

All tokens in `tokens.css` were derived from the workshop prototype's `styles.css` :root block. The original source uses these token names directly; this package maps them to Open Design's shared schema.

## Design Decisions

- `--bg: #0A0807` — deep warm black, matches workshop background
- `--surface: #16120E` — warm dark charcoal, matches workshop card backgrounds
- `--accent: #E8A04A` — amber, the primary brand color
- `--fg: #F2EDE3` — warm cream text, high contrast on dark
- `--font-display: 'Space Grotesk'` — geometric display font
- `--font-body: 'Inter'` — clean body font

## Verification

Token values were verified against the source stylesheet. Line numbers in `token-contract.report.json` reference the `tokens.css` file in this package.
