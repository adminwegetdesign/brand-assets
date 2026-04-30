# Fonts

Lexend lives here. **ITC Avant Garde Gothic does not** — it's a licensed display font and we don't redistribute it.

For the canonical typography rules — when to use which face, sanctioned weights, sizing — see [`guidelines/wgd-brand-guidelines.md`](../guidelines/wgd-brand-guidelines.md).

## What's in this folder

Lexend ships as a **variable font** — one file covers every weight from 100 (Thin) to 900 (Black) via the `wght` axis. No need for separate per-weight files.

| File | Format | Use |
|---|---|---|
| `lexend-variable.woff2` | Variable woff2 | Web — modern browsers |
| `lexend-variable.ttf` | Variable TrueType | Desktop, Office, PDF |
| `OFL.txt` | Licence | SIL Open Font License 1.1 |

## Sanctioned weights

The PDF sanctions five weights. Use the matching CSS `font-weight` numbers when applying the variable font:

| Keyword | CSS weight | Use |
|---|---|---|
| Light | 300 | Captions, fine print |
| Regular | 400 | Body copy |
| Medium | 500 | Emphasis |
| Semi-bold | 600 | Sub-headings, strong emphasis |
| Bold | 700 | Headings |

Don't use weights outside this set without a brand-rule update — the PDF doesn't sanction Thin (100), Extra-light (200), Extra-bold (800) or Black (900).

## Consuming

Pin to `main` via raw URL:

```
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.woff2
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.ttf
```

In CSS:

```css
@font-face {
  font-family: 'Lexend';
  src: url('https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.woff2') format('woff2-variations'),
       url('https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.woff2') format('woff2');
  font-weight: 100 900;
  font-display: swap;
}

body { font-family: 'Lexend', sans-serif; font-weight: 400; }
h1   { font-weight: 700; }
.note { font-weight: 300; }
```

For pure web work, the Google Fonts CDN is also fine — Lexend is freely available there:

```html
<link href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

The repo copies are for offline use, Office docs, PDFs, or any context where pinning a known version matters more than CDN convenience. Install the `.ttf` on your machine for desktop / Office work.

## Why no ITC Avant Garde?

It's a licensed font, used only for the logomark and display headlines. The licence forbids redistribution. If you need it for a deliverable, install it on your own machine via your own licence — don't try to grab it from this repo.

If you're producing web work and need a display face, use Lexend at weight 700 (Bold) instead. It's not the same, but it's the sanctioned web fallback.

## Naming

- Kebab-case, lowercase: `lexend-variable.woff2`. Never `Lexend-Variable.WOFF2`, `lexend_variable.woff2`, or `Lexend Variable.woff2`.
- Format conveyed by extension only — `lexend-variable.woff2` and `lexend-variable.ttf` differentiate themselves.
- If a non-variable static file ever ships (e.g. for a tool that doesn't support variable fonts), use the weight keyword: `lexend-regular.woff2`, `lexend-bold.woff2` — never weight numbers (`lexend-400.woff2`) or abbreviations (`lexend-reg.woff2`).

## Licence

Lexend is OFL-licensed (SIL Open Font License 1.1). Free to use, modify, and redistribute. The full licence travels with the font files in `OFL.txt`.

## Don't

- Don't commit ITC Avant Garde files. Ever.
- Don't use weights outside the five sanctioned ones (300, 400, 500, 600, 700).
- Don't ship italic variants without a brand-rule update — the PDF doesn't sanction italics.
- Don't pin consumer URLs to commit hashes or tags. `main` is the contract.
