# WGD Brand Guidelines

Living guidelines for the WeGetDesign visual identity. Synced with the 2024 source PDF (archived at `guidelines/archive/wgd-brand-guidelines-2024.pdf`). When the PDF and this doc disagree, the PDF wins for visual rules — update this doc to match. When this doc and the repo disagree, fix whichever is wrong; both should track each other.

> Don't invent rules. New rules come from the brand guide PDF or explicit instruction from Omar.

---

## 1. Logo system

### Variants

The PDF defines **four** logo structures across two axes — colour vs. monochromatic, and positive vs. negative (light vs. dark background).

| Structure | Description | Repo folder |
|---|---|---|
| **Positive colour** | Full colour (teal + lime) on light background | `logos/positive/` |
| **Negative colour** | Full colour on dark background | _not yet in repo_ |
| **Positive monochromatic** | Single-colour teal on light background | `logos/mono-teal/` |
| **Negative monochromatic** | Single-colour white on dark background | `logos/mono-white/` |

Source PDF caption: _"opposite are the structures for using the identity in a positive, negative and monochromatic system."_ The PDF marks the colour identities as primary and instructs that they "should always be prioritised where possible."

> **Gap:** the negative-colour variant (full-colour logo on dark) is described in the PDF but has no folder in this repo. Producing those exports is an open follow-up.

### Lockups

Each variant ships the same five lockups:

| Lockup | Filename stem | When to use |
|---|---|---|
| **Master** | `wgd-logo-master` | Default. Use unless the space demands something else. |
| **Landscape** | `wgd-logo-landscape` | Wide / horizontal spaces (banners, headers, footers). |
| **Tall** | `wgd-logo-tall` | Narrow / vertical spaces (sidebars, mobile splash). |
| **Left-aligned** | `wgd-logo-left-aligned` | Layouts that need the wordmark flush left. |
| **Icon** | `wgd-logo-icon` | The Q / circle-and-curser mark only, no wordmark. Favicon, app icon, social avatar. |

The PDF refers to the icon as the "logomark" and notes it has two visual elements: a **circle** ("a team or business that wegetdesign would be aiming to help or work with") and a **curser** ("partially merged with the circle… a universal indicator that can be linked with the services wegetdesign offer. the overlap represents how we integrate"). Don't separate the two.

### File formats per variant

The PDF doesn't prescribe formats; this is repo policy:

- **Positive** and **mono-teal**: `.png` + `.jpg` for every lockup; `.ai` + `.pdf` masters for the primary master lockup.
- **Mono-white**: `.png` only for every lockup (PNG transparency required — white-on-white JPG is unusable); `.ai` + `.pdf` masters for the primary master lockup.

### Choosing a variant

1. Light background → positive colour (default).
2. Dark background, single-colour reproduction available → mono-white.
3. Light background, single-colour reproduction required → mono-teal.
4. Dark background, full-colour reproduction available → negative colour _(not yet exported)_.

---

## 2. Typography

The PDF defines two typefaces, each with a fixed role.

### Display / logo type — ITC Avant Garde Gothic

Used inside the logomark and in display/headline contexts. Licensed font; **never embed or commit the font files to this repo**.

Weights sanctioned by the PDF:
- **Demi**
- **Book**

> CLAUDE.md previously listed "demi, bold". The PDF only shows demi and book — the doc above reflects the PDF.

### Body / web type — Lexend

Google Font. Web-safe, free to use across all platforms. The PDF caption: _"as this font is a web friendly google font it can be used across all platforms."_

Weights sanctioned by the PDF:
- **Bold**
- **Semi-bold**
- **Medium**
- **Regular**
- **Light**

> CLAUDE.md previously listed only four (light, regular, medium, semi-bold). The PDF includes bold; the doc above reflects the PDF.

### Use cases

| Context | Typeface | Weight |
|---|---|---|
| Logomark wordmark | ITC Avant Garde Gothic | Demi |
| Display headlines | ITC Avant Garde Gothic | Demi or Book |
| Web body copy | Lexend | Regular |
| Web emphasis | Lexend | Medium / Semi-bold |
| Web headings | Lexend | Bold / Semi-bold |
| Captions / fine print | Lexend | Light |

---

## 3. Colour

### Primary palette

Always pair teal + lime. Never substitute either with an approximation.

| Name | Hex | RGB | CMYK | Pantone |
|---|---|---|---|---|
| Teal | `#004751` | 0, 71, 81 | 98, 48, 49, 46 | 316c |
| Lime | `#CAD500` | 202, 213, 0 | 29, 0, 98, 0 | 381c |

### Secondary palette

For marketing material. Six swatches:

| Name | Hex | RGB | CMYK | Pantone |
|---|---|---|---|---|
| Slate blue | `#4B6775` | 75, 103, 117 | 72, 46, 38, 25 | 6116c |
| Dark grey | `#53565B` | 83, 86, 91 | 63, 51, 46, 40 | Cool Gray 11c |
| Light grey | `#CFD2D3` | 207, 210, 211 | 22, 14, 16, 0 | 427c |
| Pale lime | `#E2E9B9` | 226, 223, 185 | 15, 2, 36, 0 | 6190c |
| Aqua | `#50BAAD` | 80, 186, 173 | 66, 0, 39, 0 | 3258c |
| Lime (alt) | `#CAD500` | 202, 213, 0 | 29, 0, 98, 0 | 395c |

> **Note on Pantone 395c.** The PDF lists this in the secondary palette with the same hex (`#CAD500`) as the primary lime (381c). Treat it as an alternate Pantone reference for the same digital colour, useful when 381c is not available in print.

### Accessibility notes

The source PDF does **not** specify contrast ratios or WCAG targets. The notes below are derived from the palette plus standard WCAG 2.1 AA — flagged as derived, not from the brand guide.

- **Teal `#004751` on white** — passes WCAG AA for normal body text.
- **Lime `#CAD500` on white** — fails WCAG AA for body text. Use lime only as an accent, on teal backgrounds, or for large display type. Never run body copy in lime on white.
- **White `#FFFFFF` on teal `#004751`** — passes WCAG AA. This is the primary dark-background pairing.
- **Teal on lime / lime on teal** — passes WCAG AA at large sizes only; verify per use.
- **Slate blue, dark grey, light grey, pale lime, aqua** — verify contrast per use; none of these are sanctioned for body copy on white without checking.

When in doubt, hold body text in `#004751` (teal) or `#53565B` (dark grey) on a `#FFFFFF` or `#CFD2D3`-or-lighter background.

---

## 4. Spacing & sizing

### Clear space (safety area)

Use the lowercase **d** of the wordmark as the safety-area unit. Maintain at least one "d" of clear space on all four sides of the logo when placing it against other graphics, borders, or page edges.

### Internal dividers

Spacing inside the logomark is derived from the wordmark itself:

- Lowercase **d** divides the logomark (icon) from the wordmark.
- Lowercase **e** divides the wordmark from the strapline.

PDF wording: _"we use the type elements from within the main typographic structure as spacers."_

### Minimum sizes

For legibility. The PDF requests these as the smallest scales of the logo.

| Asset | Minimum |
|---|---|
| Full lockup (any) | **L = 30 mm** print, or **150 px @ 72 dpi** screen |
| Icon only | **L = 30 mm** print, or **150 px @ 72 dpi** screen |
| Wordmark only | **H = 10 mm** print, or **50 px @ 72 dpi** screen |

---

## 5. Voice & positioning

### Strapline

> `discover, design, develop.`

Always lowercase. Always with the trailing period. Always as a comma-separated triplet — never split, never reordered.

### Positioning lines

From the PDF, in their original lowercase form:

- _your long term development partner_
- _foundations for today and tomorrow, we develop tech that's set to grow_

### The three pillars

The PDF expands the strapline into three service pillars. Use the language below verbatim when describing what we do.

- **discover** — _"a dedicated learning phase where we integrate our team into your planning process. Through workshops, we aim to understand any issues and inefficiencies in your project and business. Based on these insights, we work on designing systems that effectively deliver results."_
- **design** — _"Following the discovery phase, we transition to design. We incorporate our insights into a visual design phase, collaborating with you to meet your brand requirements. The result is a bespoke set of interface designs tailored for your needs."_
- **develop** — _"Using Bubble.io as our foundation, we bring your design visions to life. Together, we'll map out your database structures, sort out your style sets, and craft your application from the ground up. It's a partnership every step of the way."_

### Address

> 31 Windsor Place, Cardiff, CF10 3BZ

---

## 6. Asset index

This section reflects what is **actually in the repo** at the time of writing. Update whenever assets are added, removed, or renamed — the asset index and the live tree must always agree.

### `logos/positive/` — positive colour

| File | Format | Notes |
|---|---|---|
| `wgd-logo-master.ai` | Vector source | Master |
| `wgd-logo-master.pdf` | Vector | Master |
| `wgd-logo-master.png` | Raster | Master |
| `wgd-logo-master.jpg` | Raster | Master |
| `wgd-logo-landscape.png` | Raster | Landscape lockup |
| `wgd-logo-landscape.jpg` | Raster | Landscape lockup |
| `wgd-logo-tall.png` | Raster | Tall lockup |
| `wgd-logo-tall.jpg` | Raster | Tall lockup |
| `wgd-logo-left-aligned.png` | Raster | Left-aligned lockup |
| `wgd-logo-left-aligned.jpg` | Raster | Left-aligned lockup |
| `wgd-logo-icon.png` | Raster | Icon / Q-mark only |
| `wgd-logo-icon.jpg` | Raster | Icon / Q-mark only |
| `wgd-logo-signature.png` | Raster | **Stray — not a sanctioned lockup. Pending sign-off on whether to remove or whether the lockup list should expand.** |

### `logos/mono-teal/` — positive monochromatic

| File | Format | Notes |
|---|---|---|
| `wgd-logo-master.ai` | Vector source | Master |
| `wgd-logo-master.pdf` | Vector | Master |
| `wgd-logo-master.png` | Raster | Master |
| `wgd-logo-master.jpg` | Raster | Master |
| `wgd-logo-landscape.png` / `.jpg` | Raster | Landscape lockup |
| `wgd-logo-tall.png` / `.jpg` | Raster | Tall lockup |
| `wgd-logo-left-aligned.png` / `.jpg` | Raster | Left-aligned lockup |
| `wgd-logo-icon.png` / `.jpg` | Raster | Icon |

### `logos/mono-white/` — negative monochromatic

PNG-only by design — JPG cannot carry transparency, and a white logo on a white JPG background is unusable.

| File | Format | Notes |
|---|---|---|
| `wgd-logo-master.ai` | Vector source | Master |
| `wgd-logo-master.pdf` | Vector | Master |
| `wgd-logo-master.png` | Raster | Master |
| `wgd-logo-landscape.png` | Raster | Landscape lockup |
| `wgd-logo-tall.png` | Raster | Tall lockup |
| `wgd-logo-left-aligned.png` | Raster | Left-aligned lockup |
| `wgd-logo-icon.png` | Raster | Icon |

### Negative colour _(not in repo)_

The PDF specifies a fourth structure — the full-colour logo on a dark background. No assets exist for this yet. Should land in `logos/negative/` when produced, mirroring the five-lockup shape of the other variants.

### `fonts/`

_Currently empty._ Will hold the Lexend variable font (one file covering all sanctioned weights via the `wght` axis), plus the OFL licence. ITC Avant Garde Gothic is licensed and **must not** be committed.

### `colours/`

_Currently empty._ Will hold:
- `tokens.json` — palette as Design Tokens CG JSON.
- `tokens.css` — palette as CSS custom properties.

`colours/tokens.json` is referenced in the consumer-contract example in CLAUDE.md, so any downstream skill expecting that URL is currently 404ing. Producing these files is an open follow-up.

---

## Maintenance

- This document is the asset index and the rule book. Both must stay in sync with the repo.
- The 2024 source PDF lives at `guidelines/archive/wgd-brand-guidelines-2024.pdf`. Open it for visual examples and pixel-exact reference.
- Changes to brand rules require Omar's sign-off and a PR — never push to `main` directly.
