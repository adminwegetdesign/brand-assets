
# WGD Brand Assets — Custodian Context

## Purpose

Canonical home for WeGetDesign visual and brand assets. Referenced via raw GitHub URLs by all WGD Claude skills, internal tools, and client deliverables. The contract with consumers is simple: **`main` is always trustworthy**.

## Brand fundamentals

Source of truth: the WGD Brand Guidelines (2024) PDF, archived in `guidelines/`.

### Primary palette

| Colour | Hex | RGB | CMYK | Pantone |
|---|---|---|---|---|
| Teal | `#004751` | 0, 71, 81 | 98, 48, 49, 46 | 316c |
| Lime | `#CAD500` | 202, 213, 0 | 29, 0, 98, 0 | 381c |

Always pair teal + lime. Never substitute either with an approximation.

### Secondary palette (marketing material)

| Colour | Hex | Pantone |
|---|---|---|
| Slate blue | `#4B6775` | 6116c |
| Pale lime | `#E2E9B9` | 6190c |
| Dark grey | `#53565B` | Cool Gray 11c |
| Aqua | `#50BAAD` | 3258c |
| Light grey | `#CFD2D3` | 427c |

### Typography

- Display / logo: **ITC Avant Garde Gothic** (demi, book) — licensed font, not for embedding
- Body / web: **Lexend** (light, regular, medium, semi-bold, bold) — Google Font, web-safe

### Logo system

Three sanctioned variants, each in its own folder:
- `logos/positive/` — full colour (teal + lime). Default. Use on white or light backgrounds.
- `logos/mono-teal/` — teal monochrome. Use when single colour is required and the background is light.
- `logos/mono-white/` — white monochrome. Use on dark backgrounds.

Within each variant, the same five lockups exist:
- `wgd-logo-master.{png,jpg,ai,pdf}` — primary lockup, default choice
- `wgd-logo-landscape.{png,jpg}` — horizontal lockup for wide spaces
- `wgd-logo-tall.{png,jpg}` — vertical lockup for narrow spaces
- `wgd-logo-left-aligned.{png,jpg}` — left-aligned variant
- `wgd-logo-icon.{png,jpg}` — Q icon only, no wordmark

### Logo spacing & sizing rules (from the brand guide)

- **Clear space**: the lowercase "d" of the wordmark is the safety-area unit on all four sides
- **Internal spacing**: lowercase "d" divides logomark from wordmark; lowercase "e" divides wordmark from strapline
- **Minimum sizes**:
  - Full lockup: L=30mm or 150px @ 72dpi
  - Icon only: L=30mm or 150px
  - Wordmark only: H=10mm or 50px

### Tagline & positioning

- Strapline: `discover, design, develop.` — always lowercase, always the trailing period
- Positioning lines (from the guide): `your long term development partner`, `foundations for today and tomorrow, we develop tech that's set to grow`

### Address

31 Windsor Place, Cardiff, CF10 3BZ

## Repo conventions

### Folder structure

| Folder | Holds |
|---|---|
| `logos/` | Logo system (positive, mono-teal, mono-white sub-folders) |
| `fonts/` | Brand typefaces — Lexend only in this repo (Avant Garde is licensed, not redistributable) |
| `colours/` | Colour tokens as JSON and CSS custom properties |
| `templates/` | Letterhead, document headers, footer artwork |
| `guidelines/` | Master `wgd-brand-guidelines.md` + archived source PDFs |

### Naming

- kebab-case, descriptive: `wgd-logo-master.png`, never `Logo1.PNG` or `WGD_LOGO_FINAL.png`
- No spaces, no parentheses, no underscores, no version numbers in filenames
- Variants suffixed: `-master`, `-icon`, `-landscape`, `-tall`, `-left-aligned`
- Format conveyed by extension only — `master.png` and `master.jpg` differentiate themselves; never write `master-png.png`

### Commit messages

Conventional, lowercase, imperative:

- `add(logos): mono-teal SVG variants`
- `update(colours): rename accent token to lime`
- `docs(guidelines): clarify logo clear-space rule`
- `refactor(fonts): split Lexend into weight files`
- `fix(readme): correct org name in raw URL examples`

### Branches

- `main` is the consumer contract. Always trustworthy.
- Feature branches: `add/<scope>`, `update/<scope>`, `fix/<scope>`, `chore/<scope>`
- One concern per branch. One concern per commit where practical.

## Consumer contract

Every WGD skill, tool, or document generator that needs a brand asset reads from a raw GitHub URL pinned to `main`. Pattern:

https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/<path>

Examples:

https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/positive/wgd-logo-master.png
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/mono-white/wgd-logo-icon.png
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.json

Consumers must never pin to commit hashes or tags. If a breaking change is unavoidable, it ships in a new path (e.g. `colours/tokens-v2.json`), never by mutating an existing one.

## Don't

- Don't push to `main` directly. Branch + PR for every change, even one-line ones.
- Don't add an asset without updating `guidelines/wgd-brand-guidelines.md` — the asset index in that doc must always reflect what's actually in the repo.
- Don't delete an asset without grep-checking which WGD repos and skills reference it. A 404 on a raw URL is silent breakage downstream.
- Don't commit ITC Avant Garde Gothic font files. Licensed font, not redistributable. Lexend is fine.
- Don't introduce spaces, parentheses, or capitals into filenames or folder names. Kebab-case only.
- Don't invent brand rules. New rules come from the brand guide PDF or explicit instruction from Omar — never from LLM intuition.
- Don't pin consumer URLs to commit hashes or tags. `main` is the contract.
- Don't compress or re-export the original `.ai` and `.pdf` source files. They're the masters.
- Don't add client-specific assets here. Those belong in the client's own project.
