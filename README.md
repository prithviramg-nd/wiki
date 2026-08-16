# wiki

A personal knowledge base written in the [Open Knowledge Format](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing) (OKF) — plain markdown files with a small YAML frontmatter schema, cross-linked, version-controlled. OKF formalizes the ["LLM wiki"](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) pattern popularized by Andrej Karpathy: a compounding, agent-maintained wiki instead of RAG-from-scratch over raw sources.

Published as a static site with [Quartz](https://quartz.jzhao.xyz) v5, deployed to GitHub Pages on every push to `main`.

## Structure

- `content/` — the wiki itself. See [CLAUDE.md](CLAUDE.md) for the page schema and conventions.
- everything else — the Quartz v5 site generator and its config (`quartz.config.yaml`).

## Local development

```bash
npm ci
npx quartz plugin install --from-config
npx quartz build --serve   # http://localhost:8080
```

## Deployment

`.github/workflows/deploy.yml` builds and deploys `content/` on every push to `main`, via GitHub Pages (Settings → Pages → Source: GitHub Actions). Live at `https://prithviramg-nd.github.io/wiki`.
