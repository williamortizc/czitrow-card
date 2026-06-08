# AGENTS.md

## Project

Personal website for `czitrow.xyz`, hosted on GitHub Pages.

The site has two parts:

- Home: static `index.html` with the cyberpunk/Matrix personal card.
- Blog: native Jekyll content generated from Markdown files.

The home must keep its current visual design unless the user explicitly asks for a redesign. Small copy/link changes are fine.

## Stack

- GitHub Pages
- Jekyll native build
- HTML, CSS, Markdown, Liquid
- No npm, no frontend framework, no external fonts/CDNs

## Important Files

- `index.html`: production home page. Keep visually stable.
- `styles.css`: shared styles for home, blog index, and posts.
- `_config.yml`: Jekyll config.
- `blog/index.html`: blog listing page. Lists `site.posts`.
- `_layouts/default.html`: base layout for Jekyll-generated pages.
- `_layouts/post.html`: layout for blog posts.
- `_includes/matrix-background.html`: shared animated background for blog pages.
- `_posts/`: public blog posts. Anything here is published by GitHub Pages.
- `_drafts/`: drafts/backups. These are not published by GitHub Pages by default.
- `BLOG.md`: maintainer documentation and writing workflow.
- `CNAME`: custom domain. Leave as `czitrow.xyz`.

## Blog Workflow

Public posts go in `_posts/` using this filename format:

```text
YYYY-MM-DD-title-slug.md
```

Each post must start with YAML front matter:

```md
---
title: "Post title"
date: 2026-06-08
description: "Short summary for the blog index."
tags: [linux, terminal, notes]
---
```

Drafts or backups go in `_drafts/`. Do not move a draft into `_posts/` unless the user wants it public.

If there are no public posts, `/blog/` should show the empty state.

## Deployment

After approved content/code changes:

```bash
git add <changed files>
git commit -m "<clear message>"
git push origin main
```

GitHub Pages builds Jekyll automatically after push. Production can take a few minutes to update because of GitHub/Fastly/Cloudflare caching.

When changing `styles.css`, update the CSS query string in HTML/layout references, for example:

```html
styles.css?v=YYYYMMDD-N
```

This avoids stale cached CSS breaking the layout.

## Verification

Prefer these checks before commit/push:

```bash
git diff --check
```

Check production after push:

```bash
curl -s -I https://czitrow.xyz/
curl -s -I https://czitrow.xyz/blog/
```

If a public post is added, also verify its generated URL.

## Guardrails

- Do not publish private notes accidentally. `_posts/` is public.
- Keep drafts in `_drafts/` until the user explicitly approves publication.
- Do not commit screenshots or local image captures unless requested.
- Do not remove `CNAME`.
- Keep the home page visually consistent with the current cyberpunk card.
- Keep content in Spanish unless the user asks otherwise.
