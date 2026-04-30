# WeGetDesign Brand Assets

Canonical home for WGD visual and brand assets. Consumed via raw GitHub URLs by all WGD Claude skills, internal tools, and client deliverables.

The contract with consumers is simple: **`main` is always trustworthy**. Pin to `main`, never to a commit hash or tag.

## Usage

Reference assets via raw GitHub URLs:

```
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/positive/wgd-logo-master.png
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/logos/mono-white/wgd-logo-icon.png
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.json
https://raw.githubusercontent.com/adminwegetdesign/brand-assets/main/colours/tokens.css
```

If a breaking change to an asset is unavoidable, it ships at a new path (e.g. `colours/tokens-v2.json`). The existing URL never mutates.

## Structure

| Folder | Holds |
|---|---|
| [`logos/`](logos/) | Logo system — `positive/`, `mono-teal/`, `mono-white/` sub-folders, each with the same five lockups (master, landscape, tall, left-aligned, icon) |
| [`fonts/`](fonts/) | Lexend (Google Font, OFL-licensed). ITC Avant Garde Gothic is **not** in this repo — it's licensed and not redistributable |
| [`colours/`](colours/) | Brand colour tokens as `tokens.json` (Design Tokens CG format) and `tokens.css` (CSS custom properties) |
| `templates/` | Letterhead, document headers, footer artwork |
| [`guidelines/`](guidelines/wgd-brand-guidelines.md) | Living brand guidelines (`wgd-brand-guidelines.md`) and archived source PDFs (`archive/`) |

The full brand rules — when to use which logo, sanctioned typography weights, accessibility, spacing — live in [`guidelines/wgd-brand-guidelines.md`](guidelines/wgd-brand-guidelines.md). Each asset folder also has its own README with practical consumption notes.

## Adding or changing an asset

1. Branch off `main`. Naming: `add/<scope>`, `update/<scope>`, `fix/<scope>`, or `chore/<scope>`.
2. Place the file in the correct folder, kebab-case lowercase (e.g. `wgd-logo-master.png`, never `Logo1.PNG`).
3. Update the asset index in `guidelines/wgd-brand-guidelines.md` — that doc must always reflect what's actually in the repo.
4. Open a PR. **Never push directly to `main`.**
5. Once merged, the raw URL is immediately available to consumers.

Conventional commit messages, lowercase imperative — see `CLAUDE.md` for the full convention list.

## What this repo isn't

- A dumping ground for client work — client-specific assets belong in the client's own project.
- A place for ITC Avant Garde Gothic — licensed display font, install on your machine via your own licence.
- A place for compressed or re-exported versions of the `.ai` / `.pdf` masters — they're sources of truth, leave them alone.

## License

Brand assets © WeGetDesign. The repo structure and any open-source dependencies (e.g. Lexend under OFL) carry their own licences.
