# WeGetDesign Brand Assets

Visual and brand assets referenced by WeGetDesign Claude skills.

## Usage

Reference assets via raw GitHub URLs from your skills:

\`\`\`
https://raw.githubusercontent.com/wegetdesign/brand-assets/main/logos/wgd-primary.png
https://raw.githubusercontent.com/wegetdesign/brand-assets/main/fonts/inter-regular.ttf
\`\`\`

Always pin to `main` for now.

## Structure

- `logos/` — Primary, secondary, monochrome, favicon variants
- `fonts/` — Brand typefaces (TTF/OTF)
- `colours/` — Brand colour tokens (JSON, CSS)
- `templates/` — Letterhead, document headers, footer artwork
- `guidelines/` — Brand guidelines PDF, usage notes

## Adding assets

1. Place the file in the correct folder
2. Commit with message: `add(category): asset-name`
3. The raw URL is immediately available
4. Update any skill that needs the new asset

## License

MIT — these are WeGetDesign assets but the repo structure is open.
