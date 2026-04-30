# Colours

Brand colour tokens. The full palette, accessibility notes, and usage rules live in [`guidelines/wgd-brand-guidelines.md`](../guidelines/wgd-brand-guidelines.md) — this folder is for **machine-readable consumption**.

## What's in this folder

_Currently empty — placeholder until the token files land._

When populated, the folder will contain:

| File | Format | Use |
|---|---|---|
| `tokens.json` | Design Token JSON | Programmatic consumption (build scripts, design systems, Figma plugins) |
| `tokens.css` | CSS custom properties | Drop-in for any web project |

## Palette at a glance

### Primary — always pair these

| Name | Hex | Token |
|---|---|---|
| Teal | `#004751` | `--wgd-teal` |
| Lime | `#CAD500` | `--wgd-lime` |

### Secondary — marketing material

| Name | Hex | Token |
|---|---|---|
| Slate blue | `#4B6775` | `--wgd-slate-blue` |
| Dark grey | `#53565B` | `--wgd-dark-grey` |
| Light grey | `#CFD2D3` | `--wgd-light-grey` |
| Pale lime | `#E2E9B9` | `--wgd-pale-lime` |
| Aqua | `#50BAAD` | `--wgd-aqua` |

Print equivalents (Pantone, CMYK) and the alternate Pantone reference for lime (395c) live in the main guidelines doc.

## Consuming

Pin to `main` via raw URL:

```
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.json
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.css
```

In CSS:

```css
@import url('https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.css');

.button {
  background: var(--wgd-teal);
  color: var(--wgd-lime);
}
```

In JavaScript / TypeScript:

```js
const tokens = await fetch(
  'https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.json'
).then(r => r.json());

const teal = tokens.primary.teal.hex; // "#004751"
```

## Token shape

`tokens.json` follows the [Design Tokens Community Group format](https://design-tokens.github.io/community-group/format/):

```json
{
  "primary": {
    "teal":  { "$value": "#004751", "$type": "color" },
    "lime":  { "$value": "#CAD500", "$type": "color" }
  },
  "secondary": {
    "slate-blue":  { "$value": "#4B6775", "$type": "color" },
    "dark-grey":   { "$value": "#53565B", "$type": "color" },
    "light-grey":  { "$value": "#CFD2D3", "$type": "color" },
    "pale-lime":   { "$value": "#E2E9B9", "$type": "color" },
    "aqua":        { "$value": "#50BAAD", "$type": "color" }
  }
}
```

`tokens.css` exposes the same values as CSS custom properties on `:root`, prefixed `--wgd-`.

## Naming

- Token names: kebab-case, prefixed `--wgd-`, descriptive (`--wgd-slate-blue`, not `--wgd-secondary-1`).
- Hex values: lowercase `#004751`, six digits, no shorthand.
- File names: kebab-case (`tokens.json`, `tokens-dark.json` if a dark variant ever ships).

## Accessibility — quick rules

Full notes in [`guidelines/wgd-brand-guidelines.md`](../guidelines/wgd-brand-guidelines.md). At a glance:

- **Don't** run lime body text on white. Fails WCAG AA. Lime is an accent only.
- **Do** use teal `#004751` for body text on white or light grey. Passes AA.
- **Do** use white `#FFFFFF` for body text on teal. Passes AA.
- For any other pairing — verify per use.

## Stability — the consumer contract

If a breaking change to the palette is unavoidable, it ships under a new path (e.g. `colours/tokens-v2.json`). The existing `tokens.json` URL **never mutates** — that's the contract every downstream skill, doc generator, and template depends on.

## Don't

- Don't introduce a new colour without updating both the main guidelines doc and the token files in the same PR.
- Don't approximate any of these hex values. Teal is `#004751`, not `#005060`. Lime is `#CAD500`, not `#CCDD00`.
- Don't pin consumer URLs to commit hashes or tags. `main` is the contract.
