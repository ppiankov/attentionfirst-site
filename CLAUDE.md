# attentionfirst-site

Static single-page site for attentionfirst.dev — the front door for the watch/now/spectre/contain tool ecosystem.

## What This Is

One HTML file. No JavaScript. No build tools. Dark theme. GitHub Pages deployment.

## What This Is NOT

- Not a blog or content platform
- Not a SaaS landing page
- Not a documentation site (repos have their own READMEs)

## Structure

```
index.html          — the entire site
CNAME               — custom domain
.github/workflows/  — GitHub Pages deploy
docs/work-orders.md — implementation plan
```

## Design Rules

- Pure HTML + inline CSS. No external dependencies
- Dark theme: bg `#0E1116`, text `#CDD6E0`, meta `#7C8590`
- Max-width 640px, system fonts, line-height 1.7
- One sentence per tool description
- No animations, no tracking, no cookies
- Mobile-first. Must work at 320px

## Tool Categories

- **Watch** — boundary monitoring (trustwatch, chainwatch, pastewatch)
- **Now** — real-time triage (kubenow, infranow)
- **Spectre** — code-vs-reality drift detection (vaultspectre, clickspectre, s3spectre)
- **Contain** — ephemeral incident tooling (logtap)

## Adding a Tool

1. Add a `<div class="tool">` block under the correct category
2. Link to GitHub repo
3. One-sentence description in `<p class="tool-desc">`
4. Commit: `feat: add <toolname> to site`

## Anti-Patterns

- NEVER add JavaScript
- NEVER add external CSS frameworks
- NEVER add analytics or tracking
- NEVER create separate pages per tool
- NEVER add build tooling
