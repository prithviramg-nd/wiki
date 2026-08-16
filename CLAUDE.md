# Wiki conventions

This repo is a personal knowledge base written in the **Open Knowledge Format (OKF)** —
markdown files with a small YAML frontmatter schema, cross-linked, published as a
static site with [Quartz](https://quartz.jzhao.xyz) v5 to GitHub Pages.

Reference: https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing
(OKF formalizes the "LLM wiki" pattern: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

## Structure

- `content/` — all wiki pages. Everything else in the repo is the Quartz engine/config.
- `content/index.md` — catalog of topics, kept up to date whenever a page is added.
- `content/log.md` — append-only chronological record of what changed and when.
- `content/<topic>/<page>.md` — individual pages, grouped into topic folders.

## Page frontmatter

Every page starts with:

```yaml
---
type: Concept        # Concept | Index | Log | Source | Person | ... — free-form but consistent
title: Page Title
description: One sentence, shown in link previews and search.
resource: https://... # optional — link to the original source, if any
tags: [some, tags]
timestamp: 2026-08-16T00:00:00Z  # last-substantive-edit time
---
```

## Conventions

- Cross-link concepts with `[[relative/path|Display Text]]` wikilinks, not raw URLs, so Quartz builds backlinks/graph correctly.
- When adding a new page, add a link to it from `content/index.md` and append an entry to `content/log.md`.
- Prefer editing/extending an existing page over creating a near-duplicate one — the wiki should compound, not fragment.
- Keep pages readable as plain markdown first; frontmatter is for machine-queryable metadata, not the primary content.

## Frontend (Quartz)

- `npm install` then `npx quartz plugin install --from-config` to set up.
- `npx quartz build --serve` to preview locally at `http://localhost:8080`.
- Config lives in `quartz.config.yaml` (falls back to `quartz.config.default.yaml` if absent — don't delete the default).
- Deploys to GitHub Pages via `.github/workflows/deploy.yml` on push to `main`.
