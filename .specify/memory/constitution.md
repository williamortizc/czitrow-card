<!--
Sync Impact Report:
- Version change: N/A → 1.0.0 (initial constitution)
- Modified principles: N/A (new)
- Added sections: Core Principles, Technical Constraints, Development Workflow, Governance
- Removed sections: N/A
- Templates requiring updates:
  ✅ constitution-template.md (base template, no changes needed)
  ⚠ spec-template.md (pending — to be created in /speckit.specify phase)
  ⚠ plan-template.md (pending — to be created in /speckit.plan phase)
  ⚠ tasks-template.md (pending — to be created in /speckit.tasks phase)
- Follow-up TODOs: None
-->

# Czitrow Card Constitution

## Core Principles

### I. Static-First
This project is a **static website**. No server-side rendering, no backend, no database, no API calls at runtime. The entire site is served as flat HTML, CSS, and optional minimal JavaScript from GitHub Pages. Any dynamic behavior MUST be achieved purely through client-side means and MUST NOT be required for core content access.

### II. Single Page
The site consists of **exactly one page** (`index.html`). There are no sub-pages, no routing, no multi-page navigation. All content is visible or reachable on this single page. Future expansion to multiple pages requires a constitutional amendment.

### III. Minimal Stack
The technology stack is **HTML + CSS only**. No frameworks, no build tools, no package managers, no transpilation. JavaScript is permitted only for optional progressive enhancement and MUST NOT be required for the site to function. The project MUST build and deploy with zero build steps.

### IV. Easy to Edit and Maintain
The project MUST be editable by anyone with a text editor. No specialized tooling, no local server requirement beyond a simple file viewer, no compilation step. Adding or modifying content MUST require editing only a plain HTML file.

### V. Clean and Fast
The site MUST load fast and look clean. No heavy assets, no external dependencies that could break, no tracking scripts, no ad networks. Design is sober, readable, and responsive across mobile and desktop.

## Technical Constraints

- **Hosting**: GitHub Pages
- **Domain**: `czitrow.xyz` (via CNAME)
- **Total files**: Maximum 3 (`index.html`, `styles.css`, `CNAME`). Additional files require explicit approval.
- **External resources**: None. All CSS is local. No CDN, no Google Fonts, no third-party assets.
- **Browser target**: Modern browsers (last 2 versions of Chrome, Firefox, Safari, Edge).
- **Responsive**: MUST display correctly on mobile (320px+) and desktop.

## Development Workflow

- All changes are made directly to `index.html` and `styles.css`.
- Git is used for version control. Commits should be small and descriptive.
- Deployment is automatic via GitHub Pages on push to `main` branch.
- No CI/CD pipeline, no testing framework, no linting. This is a static site with 2-3 files.
- Review is visual: open the page, check it looks right, commit.

## Governance

This constitution supersedes all other practices. Any addition or removal of a core principle requires explicit approval from the project owner (William). Amendments must be documented with a version bump and a migration note.

- **Constitutional amendments** require owner approval and a version bump.
- **Complexity must be justified** — every new file, dependency, or feature must be explained against these principles.
- **When in doubt, cut it** — if something does not clearly serve the core principles, it does not belong.

**Version**: 1.0.0 | **Ratified**: 2026-05-10 | **Last Amended**: 2026-05-10