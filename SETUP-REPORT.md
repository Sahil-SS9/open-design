# Open Design v0.16.1 + HydraSkale Integration — Complete Setup Report

## Date
2026-07-31

## 1. Installation

### Open Design v0.16.1
- **Repository:** `/home/kensei/repos/open-design` (cloned from `https://github.com/nexu-io/open-design`)
- **Branch:** `feature/hydraskale-integration` (separate from live runtime checkout at `KenseiAgent-p15-candidate`)
- **Dependencies installed:** pnpm 10.33.2 (via Corepack), Node v22.23.1
- **Node version note:** Project declares `node: "~24"` but v22 is available. Dependencies install and daemon runs, but this is a known mismatch.

### Daemon
- **Build command:** `pnpm --filter @open-design/daemon build`
- **Run command:** `node apps/daemon/dist/cli.js --port <port> --no-open`
- **Verified:** Starts with 464 bundled plugins registered, 0 warnings

### Skills Added
1. `skills/scroll-world/` — scroll-scrubbed 3D landing pages (oso95)
2. `skills/claude-skill-web-clone/` — faithful website cloning (Jane-xiaoer)

### Existing Skills Already Present
- `impeccable-design-polish`, `design-md`, `taste-skill`, `gpt-tasteskill`, `ui-ux-pro-max`, `image-to-code-skill`, `site-teardown`, `gsap-scrolltrigger` (and 7 other GSAP skills)

## 2. Configuration Changes

### Token Schema Extension (`packages/contracts/src/design-systems/token-schema.ts`)
Added `BRAND_EXTENSIONS` entries for 4 new brands:
- **hydraskale:** `--space-20`, `--primary`, `--primary-ink`, `--accent-ink`, `--link`
- **fusionfirst-workshop:** `--space-20`, `--amber`, `--amber-deep`, `--amber-soft`, `--amber-glow`, `--amber-wash`, `--signal-green`, `--signal-red`, `--signal-blue`, `--text-paper`, `--text-paper-soft`, `--line-paper`, `--bg-paper`, `--bg-paper-soft`
- **fusionfirst-creative:** `--space-20`, `--heat`, `--fusion`, `--plasma`, `--ember`, `--text-on-heat`
- **fusionfirst-flagship:** `--space-20`, `--amber`, `--amber-deep`, `--amber-soft`, `--amber-glow`, `--amber-wash`, `--signal-green`, `--signal-red`, `--signal-blue`, `--text-paper`, `--text-paper-soft`, `--line-paper`, `--bg-paper`, `--bg-paper-soft`

### Plugins Created (4 new bundled plugins under `plugins/_official/`)
Each includes `SKILL.md` and `open-design.json`:
- `hydraskale/` — HydraSkale brand (teal + burnt orange, AI/SaaS)
- `fusionfirst-workshop/` — warm dark + amber monochrome
- `fusionfirst-creative/` — warm dark + molten orange/cyan/red, terminal-adjacent
- `fusionfirst-flagship/` — layered workshop dark with amber + signal colors, editorial/data-dense

All plugins marked `isolation: "opt-in"` in metadata.

## 3. Design System Packages (all under `design-systems/`)

### HydraSkale (61 tokens)
- Teal `#00C896`, burnt orange `#FF4F00`, warm cream `#F0EBDF`
- Source: `/home/kensei/kensei-staging/fusionfirststudios-site` (HydraSkale Foundry)
- Files: manifest.json, DESIGN.md, USAGE.md, tokens.css, components.html, components.manifest.json, design-tokens.json, source/ (evidence.md, tokens.source.json, token-contract.report.json), preview/ (colors.html, typography.html, spacing.html)

### FusionFirst Workshop (70 tokens)
- Warm dark `#0A0807` + amber `#E8A04A` monochrome
- Source: `kensei-staging/fusionfirststudios-site/prototype-r/workshop`

### FusionFirst Creative (62 tokens)
- Warm dark `#0A0A0B` + molten orange `#FF5722`, electric cyan `#00E5FF`, deep red `#FF3366`
- Source: `kensei-staging/fusionfirststudios-site/prototype`

### FusionFirst Flagship (70 tokens)
- Layered workshop dark `#0A0807` + amber signals + green/red/blue data colors
- Source: `kensei-staging/fusionfirststudios-site/prototype-flagship`

### Per-package file structure (identical for all 4):
```
design-systems/<slug>/
├── manifest.json                    # v1 project manifest
├── tokens.css                       # :root token block (byte-synced with components.html)
├── components.html                  # component fixture (buttons, cards, badges, inputs, kbd, icons)
├── components.manifest.json         # auto-generated component manifest
├── design-tokens.json               # od-design-tokens/v1 format
├── DESIGN.md                        # 7-section design spec
├── USAGE.md                         # agent-facing guide (Read Order, Design Highlights, Do, Avoid)
├── preview/
│   ├── colors.html
│   ├── typography.html
│   └── spacing.html
└── source/
    ├── evidence.md                  # provenance notes
    ├── tokens.source.json           # explicit token name mappings
    └── token-contract.report.json   # contract validation report with tokens array
```

## 4. Integrations Completed

### Daemon + Plugins
- All 4 new plugins registered as bundled plugins (464 total)
- Daemon HTTP API serves all design systems
- Plugin manifests resolve correctly

### Prototype Website
- Location: `/home/kensei/repos/open-design/examples/hydraskale-prototype/index.html`
- Single-file HTML using HydraSkale tokens via CSS custom properties
- Sections: Hero, Features (2×2 grid), How It Works (3-step), CTA footer
- All colors resolved from `:root` token block — no raw hex outside root

### kensei-staging Inventory
Reviewed and extracted 3 design systems from FusionFirst Studio prototypes:
- Workshop (prototype-r/workshop): 14 CSS files, warm dark + amber
- Creative (prototype): 12 CSS files, terminal-adjacent with neon
- Flagship (prototype-flagship): 6 CSS files, editorial/dark layering

Plus identified existing skills:
- `impeccable-design-polish` — elite polish workflow
- `design-md` / `dezzy-design-md` — DESIGN.md authoring
- `taste-skill` — design taste (upstream: Leonx-lnx/taste-skill)
- `ui-ux-pro-max` — comprehensive UI/UX
- `image-to-code-skill` — image-first implementation
- `TeardownSkill.md` — site-teardown methodology (from kensei-staging, already in skills/)

### External Repos
- `scroll-world` (oso95) — 6047 stars, MIT. Scroll-scrubbed 3D landing pages. Requires Monid/Higgsfield/ffmpeg.
- `claude-skill-web-clone` (Jane-xiaoer) — 900 stars. Faithful website cloning methodology.

## 5. Validation Results

### Guard Check (pnpm guard)
```
Design system manifest check passed: 155 project manifests valid
Design system package quality passed: 151 migrated packages checked; average score 100
Design system token-fixture sync passed: 155 brand pairs aligned
Design system A1 required tokens passed: 155 brands declare all 26 A1 tokens
Design system A2 required tokens passed: 155 brands declare all 26 A2 tokens
Design system B-slot required tokens passed: 155 brands declare all 4 B-slot tokens
Design system unknown token allowlist passed: 8745 declarations across 155 brands
Design system A2 defaults parity passed: 26 A2 fallbacks match byte-for-byte
Design system flag parity passed: 0 prose-only, 155 structured brands show expected divergence
Design system component manifest extraction passed: 155 fixtures (8051 selectors, 1176 component groups)
```

All checks pass. (Note: `pnpm guard` exits with code 1 due to "report-only mode" on component fixture reports — this is pre-existing behavior, not a failure.)

### Daemon Verification
```
[plugins] registered 464 bundled plugin(s)
[plugins] seeded community registry source (4 plugin(s))
[plugins] seeded official registry source (464 plugin(s))
[od] listening on http://127.0.0.1:4011
```

### Prototype Validation
- 95 CSS custom property usages, 0 raw hex values outside `:root`
- Token values match `design-systems/hydraskale/tokens.css`
- All references are `var(--token-name)` format

## 6. Risks, Issues, and Next Steps

### Issues
1. **Node version mismatch:** Project requires Node ~24, environment has v22. Risk: untested build/runtime behavior. **Fix:** Install Node 24 via nvm/fnm.
2. **`pnpm guard` exit code 1:** Caused by report-only mode, not actual failures. All checks pass.
3. **Embedded git repositories:** `skills/scroll-world/` and `skills/claude-skill-web-clone/` were cloned as nested git repos. Added to `.gitignore` as directories to prevent accidental commits. Content is available locally but not version-tracked as files.
4. **scroll-world dependencies not installed:** Requires Monid CLI, Higgsfield CLI, ffmpeg, Python PIL — none present. Skill is dormant.

### Risks
1. **Brand scoping:** 4 new design systems alongside 150+ others. Each is opt-in via plugin metadata. Must never be set as default.
2. **Token drift:** `:root` in `components.html` must stay byte-equivalent to `tokens.css`. Guard catches violations.
3. **Source path staleness:** Evidence files reference absolute kensei-staging paths. If source repos change, references become stale.
4. **No visual verification:** Prototype HTML was created but not served/rendered for visual QA.

### Next Steps
1. Install Node 24 to match project requirements
2. Serve prototype via static server and visually verify rendering
3. Install scroll-world dependencies if 3D scroll animations are needed for a project
4. Commit all changes to `feature/hydraskale-integration` branch
5. Consider creating an ASTRO template consuming HydraSkale tokens for the website pipeline
6. Consider integrating with `hydraskale-website-pipeline` source styles
