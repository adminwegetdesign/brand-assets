# Brand-assets repo audit and naming standardisation

**Date:** 2026-04-30
**Repo:** `adminwegetdesign/brand-assets`
**Scope:** Inventory the repo, confirm the naming convention, propose any migrations, document the downstream contract.

> **Headline finding:** the repo is already in good shape. Filenames are kebab-case-clean across all 32 logo files. Fonts, colours, and guidelines are populated and named consistently. The README (post PR #4) already uses the correct org slug. **No file renames are required.** This audit is a confirmation document, not a migration plan — but it surfaces two open decisions (`signature.png`, `logos/negative/`) and documents the convention for newcomers.

---

## 1. Inventory

Counted from `git ls-files`, current `main`. 50 tracked files in total. `.gitkeep` placeholders omitted from tables below.

### `logos/positive/` — full colour, light backgrounds

| File | Format | Dimensions / size | Notes |
|---|---|---|---|
| `wgd-logo-master.ai` | Adobe Illustrator (PDF-compatible, 5pp) | 1.4 MB | Vector source of truth |
| `wgd-logo-master.pdf` | PDF (5pp) | 412 KB | Vector master export |
| `wgd-logo-master.png` | PNG RGBA | 2176 × 1449 (72 KB) | Default raster |
| `wgd-logo-master.jpg` | JPEG 300 dpi | 340 KB | Raster, opaque background |
| `wgd-logo-landscape.png` | PNG RGBA | 3731 × 928 (88 KB) | Wide lockup |
| `wgd-logo-landscape.jpg` | JPEG 300 dpi | 408 KB | Wide lockup, opaque |
| `wgd-logo-tall.png` | PNG RGBA | 1468 × 1449 (56 KB) | Vertical lockup |
| `wgd-logo-tall.jpg` | JPEG 300 dpi | 260 KB | Vertical lockup, opaque |
| `wgd-logo-left-aligned.png` | PNG RGBA | 1684 × 1781 (80 KB) | Wordmark flush left |
| `wgd-logo-left-aligned.jpg` | JPEG 300 dpi | 348 KB | Wordmark flush left, opaque |
| `wgd-logo-icon.png` | PNG RGBA | 1548 × 1581 (44 KB) | Q-mark only |
| `wgd-logo-icon.jpg` | JPEG 300 dpi | 168 KB | Q-mark only, opaque |
| `wgd-logo-signature.png` | PNG RGBA | **500 × 500** (40 KB) | **Flagged.** Stacked square lockup, not in the sanctioned list. Only exists in this folder; resolution well below the master rasters. See §2 and §4. |

### `logos/mono-teal/` — single-colour teal, light backgrounds

| File | Format | Dimensions / size | Notes |
|---|---|---|---|
| `wgd-logo-master.ai` | AI (PDF, 5pp) | 1.4 MB | Vector source |
| `wgd-logo-master.pdf` | PDF (5pp) | 408 KB | Vector master |
| `wgd-logo-master.png` | PNG RGBA | 2176 × 1449 (72 KB) | |
| `wgd-logo-master.jpg` | JPEG 300 dpi | 348 KB | |
| `wgd-logo-landscape.{png,jpg}` | PNG / JPEG | 3731 × 928 (88/416 KB) | |
| `wgd-logo-tall.{png,jpg}` | PNG / JPEG | 1468 × 1449 (56/268 KB) | |
| `wgd-logo-left-aligned.{png,jpg}` | PNG / JPEG | 1684 × 1781 (80/352 KB) | |
| `wgd-logo-icon.{png,jpg}` | PNG / JPEG | 1548 × 1581 (44/176 KB) | |

### `logos/mono-white/` — single-colour white, dark backgrounds

PNG-only by design. JPG cannot carry transparency, and a white logo on a white JPG background is unusable.

| File | Format | Dimensions / size | Notes |
|---|---|---|---|
| `wgd-logo-master.ai` | AI (PDF, 5pp) | 1.4 MB | Vector source |
| `wgd-logo-master.pdf` | PDF (5pp) | 396 KB | Vector master |
| `wgd-logo-master.png` | PNG RGBA | 2176 × 1449 (68 KB) | |
| `wgd-logo-landscape.png` | PNG RGBA | 3731 × 928 (84 KB) | |
| `wgd-logo-tall.png` | PNG RGBA | 1468 × 1449 (52 KB) | |
| `wgd-logo-left-aligned.png` | PNG RGBA | 1684 × 1781 (72 KB) | |
| `wgd-logo-icon.png` | PNG RGBA | 1548 × 1581 (40 KB) | |

### `fonts/`

| File | Format | Size | Notes |
|---|---|---|---|
| `lexend-variable.woff2` | Variable woff2 (`wght` axis 100–900) | 70 KB | Web — modern browsers |
| `lexend-variable.ttf` | Variable TrueType (`wght` axis 100–900) | 172 KB | Desktop / Office / PDF |
| `OFL.txt` | Plain text licence | 4.3 KB | SIL Open Font License 1.1 — travels with the font |
| `README.md` | Markdown | 3.7 KB | Folder consumption guide |

ITC Avant Garde Gothic is **not** in this repo (licensed display font, not redistributable). This is intentional and correct.

### `colours/`

| File | Format | Size | Notes |
|---|---|---|---|
| `tokens.json` | Design Tokens CG JSON | 1.2 KB | Machine-readable palette (primary + secondary) |
| `tokens.css` | CSS custom properties | 455 B | Drop-in `:root` declarations, prefixed `--wgd-` |
| `README.md` | Markdown | 3.7 KB | Folder consumption guide |

### `templates/`

Empty. `.gitkeep` only. No assets ship here yet.

### `guidelines/`

| File | Format | Size | Notes |
|---|---|---|---|
| `wgd-brand-guidelines.md` | Markdown | 12 KB | Living guidelines doc — the brand bible |
| `archive/wgd-brand-guidelines-2024.pdf` | PDF (18pp) | 12 MB | Source PDF for the 2024 guidelines, archived for visual reference |

### Repo root

| File | Notes |
|---|---|
| `README.md` | Consumer-facing entry doc — already correct (PR #4) |
| `CLAUDE.md` | Custodian context for AI assistants working in the repo |
| `LICENSE` | Repo licence file |
| `.claude/agents/brand-custodian.md` | Subagent definition |

### Duplicates / near-duplicates / orphans

- **`wgd-logo-signature.png`** (only in `logos/positive/`) — the only true outlier. Resolution (500×500) is an order of magnitude smaller than the other lockups (typically 1500–3700 px on the long edge), and it has no `.jpg/.ai/.pdf` siblings or matching versions in `mono-teal/` or `mono-white/`. Either a stray awaiting cleanup, or a legitimate "stacked square / social-avatar" lockup awaiting documentation and sibling production.
- No case-only or whitespace-only duplicates.
- No working-draft files (no `_v2`, `_FINAL`, `Copy of`, etc.).
- No orphans.

---

## 2. Canonical asset identification

For each logical asset, the canonical source of truth:

| Logical asset | Canonical file | Derived from / notes |
|---|---|---|
| Positive colour logo | `logos/positive/wgd-logo-master.ai` | Vector source. `.pdf` is the export master; `.png/.jpg` are derived rasters at all five lockups. |
| Mono-teal logo | `logos/mono-teal/wgd-logo-master.ai` | Same shape — vector source, then PDF + raster exports. |
| Mono-white logo | `logos/mono-white/wgd-logo-master.ai` | Same shape — but PNG-only rasters by design. |
| Negative-colour logo | _(not in repo)_ | The PDF defines a 4th structure (full-colour on dark) but no `logos/negative/` folder exists. See §4 and §7. |
| Q-icon | `logos/positive/wgd-logo-icon.png` (and parallels) | Derived from each variant's master `.ai` with the wordmark removed. |
| Body / web typeface | `fonts/lexend-variable.ttf` | Source from `google/fonts` upstream. `lexend-variable.woff2` is derived via `woff2_compress`. |
| Display / logo typeface | _(not redistributable)_ | ITC Avant Garde Gothic is licensed; install per-machine. |
| Colour palette | `colours/tokens.json` | Design Tokens CG format. `tokens.css` is the derived CSS form. |
| Brand rule book | `guidelines/wgd-brand-guidelines.md` | Living markdown doc. The archived PDF is the historical source the doc was distilled from. |

### Working drafts to flag

- `logos/positive/wgd-logo-signature.png` — outside the sanctioned five-lockup list. Cannot be confidently called canonical or draft without Omar's call (see §4).

---

## 3. Proposed naming convention

The repo already follows a consistent convention. This section documents it explicitly so future contributors and any new Claude session can pattern-match without ambiguity.

### Universal rules (all folders)

- All lowercase.
- Hyphens — never underscores, never spaces, never parentheses.
- No version numbers in active asset filenames. Use `git` for versioning. The single exception is dated archived guidelines docs (`guidelines/archive/wgd-brand-guidelines-2024.pdf`) which encode a year because they're snapshots-in-time.
- File extensions match content: `.svg` or `.ai` for vector, `.png` or `.jpg` for raster, `.pdf` for vector documents, `.ttf`/`.otf`/`.woff2` for fonts, `.json`/`.css` for tokens, `.md` for docs.
- No two files differ only in capitalisation or whitespace.
- Format is conveyed by extension alone — never `master-png.png` or `master.png.png`.

### Logos — `logos/[variant]/[lockup].ext`

Pattern: `wgd-logo-[lockup].[ext]` inside a colour-mode parent folder.

- Variants (parent folders): `positive/`, `mono-teal/`, `mono-white/`. (A 4th, `negative/`, is described by the brand guide but not yet in the repo — see §7.)
- Lockup suffixes: `master`, `landscape`, `tall`, `left-aligned`, `icon`. These map to the five sanctioned lockups in the brand guide.
- Format suffix is the extension only.

> **Rationale for folder-encodes-colour-mode.** The brief proposed flat names like `wgd-primary-colour.png` and `wgd-icon-white.svg`. The current pattern (`wgd-logo-icon.png` inside `logos/mono-white/`) is more concise, mirrors the brand guide's structural distinction between "structures" (colour modes) and "lockups", and avoids cartesian-product filename explosion when a new colour mode lands. **Convention stays as-is.**

### Fonts — `fonts/[family]-[variant].[ext]`

- Family is lowercase: `lexend`.
- Variant is either `variable` (preferred — Lexend is a variable font) or a CSS weight keyword (`light`, `regular`, `medium`, `semi-bold`, `bold`) for static fallback files. Never weight numbers (`lexend-400.woff2`) or abbreviations (`lexend-reg.woff2`).
- Extension only: `.woff2`, `.ttf`, `.otf`.
- Licence files live alongside: `OFL.txt` for OFL-licensed fonts.

> **Rationale for `lexend-variable` over per-weight files.** Lexend ships only as a variable font upstream from Google Fonts; static-weight files don't exist there. One variable file covers all five sanctioned weights via the `wght` axis at lower total bytes than five static weights. **The brief's `inter-regular.ttf` example was outdated placeholder copy from the old README — Inter is not a WGD typeface.**

### Colours — `colours/tokens.[json|css]`

- Token file is `tokens.json` in [Design Tokens Community Group format](https://design-tokens.github.io/community-group/format/).
- CSS form is `tokens.css` exposing the same values as `--wgd-*` custom properties on `:root`.
- Token names inside the JSON / CSS: kebab-case, namespaced. Primary: `primary.teal`, `primary.lime`. Secondary: `secondary.slate-blue`, `secondary.dark-grey`, etc.
- Hex values lowercase (`#004751`), six digits, no shorthand.
- If a breaking change is unavoidable, ship under a new path: `tokens-v2.json`. The original URL never mutates — that's the consumer contract.

> **Rationale for `tokens.json` not `colours.json`.** Design Tokens CG format is the W3C-track convention; `style-dictionary`, `terrazzo`, and Figma token plugins all expect a file called `tokens.json`. Renaming to `colours.json` would lose tooling compatibility for marginal naming clarity. **Convention stays as-is.**

### Templates — `templates/[purpose]-[type].[ext]`

Forward-looking — folder is empty today. Pattern when assets land:
- Purpose: short kebab-case noun (`letterhead`, `report-cover`, `email-footer`).
- Type: format/size variant where useful (`letterhead-a4.pdf`, `report-cover-1200.png`).
- One concept per filename. No bundled templates.

### Guidelines — `guidelines/`

- Living doc: `wgd-brand-guidelines.md`. Always this exact name. Edit in place, version through `git`.
- Archived sources: `guidelines/archive/wgd-brand-guidelines-[YEAR].pdf`. Year-stamped because they're snapshots; brief's `-v[N]` versioning hasn't been needed and date is more meaningful for design-language drift.
- Folder READMEs (`fonts/README.md`, `colours/README.md`) are practical consumption guides — separate from the rule book.

---

## 4. Migration plan

**No file renames required.** Every asset already conforms to the convention in §3.

To avoid the brief's expectation of a "current → proposed" table going unanswered: the table is empty. The inventory in §1 is the evidence.

### Open decisions (not renames)

These two items need resolution but neither is a rename. Recording here so they're not lost:

| Item | What | Decision needed |
|---|---|---|
| `logos/positive/wgd-logo-signature.png` | Stacked square lockup (Q over two-line wordmark, no strapline). 500×500 PNG. Exists only in `positive/`. Not in the sanctioned five-lockup list. | **Omar's call.** Either: **(a)** delete as a stray (`chore(logos): remove unsanctioned signature lockup`), or **(b)** sanction as a 6th lockup, which triggers follow-on work — produce `.jpg/.ai/.pdf` siblings in `positive/`, then matching mono-teal and mono-white versions, plus update CLAUDE.md and the guidelines doc lockup table. |
| `logos/negative/` (missing) | The 2024 brand guide defines four logo structures: positive colour, **negative colour** (full-colour on dark), positive monochromatic, negative monochromatic. The repo has the latter three. The negative-colour folder doesn't exist. | **Design call.** Needs `.ai` re-export from the master with appropriate text-colour treatment for dark backgrounds (the wordmark colour likely changes — not safe to derive via raster compositing). Once exported, slot into `logos/negative/` with the standard five lockups. |

### Files to archive or delete

None at present. `wgd-logo-signature.png` is a candidate for deletion **only if** decision (a) is taken on the open item above.

---

## 5. README update

The README on `main` (post PR #4) is already correct:
- Org slug: `adminwegetdesign` ✓
- File references: real (`logos/positive/wgd-logo-master.png`, `colours/tokens.json` etc.) ✓
- Folder description: matches current structure ✓
- Branch + PR workflow: documented ✓
- Pointer to the living guidelines doc: present ✓

**No replacement text proposed.** The brief's update points are all already in place.

### Optional small additions (not required)

If the user wants to tighten the consumer contract further, two small additions to the README would be useful but are not blocking:

1. **Canonical asset list block** — an explicit table of the small set of URLs that downstream skills should treat as stable. Suggested location: between the existing Usage section and Structure section.

   Suggested content (for review, not committed):
   ```markdown
   ### Canonical assets — stable URLs

   | Asset | URL |
   |---|---|
   | Primary logo (raster) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/positive/wgd-logo-master.png |
   | Primary logo (vector) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/positive/wgd-logo-master.pdf |
   | Q-icon (positive) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/positive/wgd-logo-icon.png |
   | Q-icon (mono-white, for dark backgrounds) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/mono-white/wgd-logo-icon.png |
   | Lexend (variable, web) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.woff2 |
   | Lexend (variable, desktop) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/fonts/lexend-variable.ttf |
   | Colour tokens (JSON) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.json |
   | Colour tokens (CSS) | https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.css |
   ```

2. **Stability note** — one-liner near the top stating that filenames in `main` are stable; renames require a migration plan because they break downstream references.

   Suggested content (for review, not committed):
   ```markdown
   > **Stability:** filenames on `main` are part of the consumer contract. Don't rename without a migration plan — every rename has the potential to break a downstream skill silently.
   ```

If desired, these would land as a single follow-up: `update(readme): add canonical asset list and stability note`.

---

## 6. Downstream impact

### Search performed

Via `gh api search/code` (logged in as `wgd-omar` with read access to public repos):

| Query | Results |
|---|---|
| `org:adminwegetdesign brand-assets` | **0** |
| `raw.githubusercontent.com/adminwegetdesign/brand-assets` | **0** |

### Org / account inventory

- **`adminwegetdesign` org:** one repo only — `brand-assets` itself. No `wgd-skills`, no `wegetdesign-pdf-reports`, no other consumers.
- **`wgd-omar` account:** three personal repos (`candygen`, `website_segments`, a `templates` fork of sendwithus) — none reference brand-assets.

### Conclusion

No public downstream consumers of the brand-assets URLs are visible from this environment. Either:
- Downstream consumers are private (in accounts the audit can't see), **or**
- Consumers don't yet exist — the brand-assets repo is ahead of the skills that will consume it.

Either way, **the rename risk today is low** because there's nothing visible to break. This will change as soon as `wgd-skills` or `wegetdesign-pdf-reports` is created, at which point any rename must be searched against the broader org first and coordinated with affected repos.

### Recommendation for downstream consumers when they appear

- Pin to `main`, never to a commit hash or tag.
- Reference the canonical assets listed in §5 (or in the README's canonical-assets block if added).
- Treat any 404 from a raw URL as a P1 — `main` is the contract.

---

## 7. Recommended commit sequence

For the two open follow-ups in §4, plus a generic guard rail for any future rename.

### Sequence

1. **Resolve the `signature.png` decision.** Two paths, mutually exclusive:
   - **(a) Delete:** branch `chore/remove-signature-lockup`. `git rm logos/positive/wgd-logo-signature.png`. Update `guidelines/wgd-brand-guidelines.md` asset index to drop the row. Commit: `chore(logos): remove unsanctioned signature lockup`.
   - **(b) Sanction:** branch `add/signature-lockup`. Produce `.jpg/.ai/.pdf` siblings for `logos/positive/wgd-logo-signature.*`, then matching versions in `mono-teal/` and `mono-white/`. Update CLAUDE.md sanctioned-lockup list (5 → 6 lockups) and the guidelines doc Lockups table. Commit: `add(logos): sanction signature as 6th lockup with mono-teal and mono-white siblings`.

2. **Add `logos/negative/`.** Branch `add/negative-colour-lockups`. Slot exported PNGs (and PDF/AI for the master) into `logos/negative/` matching the five-lockup shape. Update CLAUDE.md (3 → 4 sanctioned variants), the guidelines doc Variants table (drop the "_not yet in repo_" note), and the asset index. Commit: `add(logos): negative-colour lockups for dark backgrounds`.

3. **Optional README polish (§5).** Branch `update/readme-canonical-list`. Adds the canonical-assets block and stability note. Commit: `update(readme): add canonical asset list and stability note`.

### How to avoid breaking skills mid-migration (general rule)

If a rename ever does become necessary in the future:

1. **Search first.** `gh api search/code -f q="<old-filename> org:adminwegetdesign"`. Also grep any private-org repos you have access to. Anywhere the old name appears must be updated in lockstep.
2. **Add new before removing old.** Land the new path first (`add(logos): X at new path`). Update consumers. **Then** remove the old in a separate PR (`chore(logos): remove X at old path`). Never rename in one step — always add-then-remove with a coordinated update window.
3. **Use `git mv`** for any rename to preserve history.
4. **Treat the URL contract as immutable for breaking changes.** If file content changes meaning, ship at a new path (`tokens-v2.json`), don't mutate the existing one.
5. **Document the rename.** A `MIGRATIONS.md` at repo root listing past renames + their reasoning would help future Claude sessions and team members. Not required today, but a good thing to add the first time we do rename.

---

## Appendix: how to read this audit

- The brief proposed specific names (`wgd-primary-colour.png`, `inter-regular.ttf`, `colours.json`). Where those conflict with current `main`, §3 explains the rationale for keeping the existing names. The conflicts come from the brief being authored before PRs #3–#6 merged; nothing in `main` needs to change to satisfy the brief's intent (predictable names, accurate README, single source of truth for colours).
- The two open items in §4 are the only actionable work that emerged from this audit. Everything else is documentation.
- This document does **not** modify the repo. It's a snapshot for review at `naming-audit-2026-04-30.md`.
