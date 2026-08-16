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
- `raw/<topic>/<file>` — the original source file the user shared (as-is), when there is one. Lives outside `content/` so Quartz never builds/publishes it as a page. The polished page's `resource:` frontmatter points to it (relative path, e.g. `raw/computer-vision/my-notes.md`) alongside external source URLs. Note: this repo is public, so anything under `raw/` is visible in the GitHub file browser (just not on the built site) — fine for public-ish notes, worth flagging to the user before saving anything sensitive there.

## Page frontmatter

Every page starts with:

```yaml
---
type: Concept        # Concept | Index | Log | Source | Person | ... — free-form but consistent
title: Page Title
description: One sentence, shown in link previews and search.
resource: https://... # optional — link to the original source: external URL, or a raw/<topic>/<file> path
tags: [some, tags]
timestamp: 2026-08-16T00:00:00Z  # last-substantive-edit time
---
```

## Conventions

- Cross-link concepts with `[[relative/path|Display Text]]` wikilinks, not raw URLs, so Quartz builds backlinks/graph correctly.
- When adding a new page, add a link to it from `content/index.md` and append an entry to `content/log.md`.
- Prefer editing/extending an existing page over creating a near-duplicate one — the wiki should compound, not fragment.
- Keep pages readable as plain markdown first; frontmatter is for machine-queryable metadata, not the primary content.
- The user shares source material (a file, a link, pasted notes) and expects it turned into page(s) here — they don't manage git themselves for this. Show a summary of the page(s) you'd add/change and wait for explicit go-ahead before committing/pushing; don't push automatically.
- **Prefer showing over telling.** Where the source material supports it, include: the actual formulas (not just prose paraphrase), a plain-language explanation of what each term/variable means and why the formula holds, a table when comparing options/variants/results, and a `\`\`\`mermaid` flow/sequence diagram for anything that's a pipeline, architecture, or multi-step process. Don't force these where they don't fit (e.g. a purely conceptual or historical note) — the bar is "does this make the idea click faster," not "does every note have four sections."
- Math: inline `$...$`, block `$$...$$` (KaTeX). Diagrams: fenced `\`\`\`mermaid` blocks — rendered client-side, no special wrapper needed. See a worked example in [[computer-vision/principal-masked-autoencoder|PMAE]].

## Ingesting from Notion

Notion page images are served via presigned S3 URLs with a 5-minute (`X-Amz-Expires=300`) TTL. Fetch the page and immediately `curl` every image URL in the same turn (one Bash call, parallel `&` jobs) — don't batch many URLs through an intermediate file write first, since generating a large JSON/text blob can itself burn through the window before any download starts. If a URL expires (`AccessDenied: Request has expired`), re-fetch the page for fresh URLs and retry immediately.

## Frontend (Quartz)

- `npm install` then `npx quartz plugin install --from-config` to set up.
- `npx quartz build --serve` to preview locally at `http://localhost:8080`.
- Config lives in `quartz.config.yaml` (falls back to `quartz.config.default.yaml` if absent — don't delete the default).
- Deploys to GitHub Pages via `.github/workflows/deploy.yml` on push to `main`.
