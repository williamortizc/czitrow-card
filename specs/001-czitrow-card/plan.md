# Implementation Plan: Czitrow Card

**Branch**: `001-czitrow-card` | **Date**: 2026-05-10 | **Spec**: [spec.md](./spec.md)
**Input**: Feature specification from `/specs/001-czitrow-card/spec.md`

## Summary

A minimal single-page personal card website for the domain `czitrow.xyz`. The page displays the owner's name ("William Ortiz"), a Spanish-language tagline, 3 external links, a brief site description, and a footer — all on one page. Built with plain HTML and CSS (no frameworks, no build step, no JavaScript required). Deployed on GitHub Pages with a custom domain. Dark color scheme, minimalist aesthetic, zero external dependencies.

## Technical Context

**Language/Version**: HTML5 + CSS3 (no JavaScript required for core functionality)
**Primary Dependencies**: None. Zero external dependencies.
**Storage**: N/A (static files only, no database)
**Testing**: Visual/manual — open in browser, check layout and responsiveness. No automated testing framework.
**Target Platform**: GitHub Pages (static site hosting), modern browsers (last 2 versions of Chrome, Firefox, Safari, Edge)
**Project Type**: Static website (single page)
**Performance Goals**: Page loads in under 2 seconds with only 2 HTTP requests (HTML + CSS). Zero external resource requests.
**Constraints**: Maximum 3 files (index.html, styles.css, CNAME). No build step. No frameworks. No external fonts or CDN. All content in Spanish. Dark theme only.
**Scale/Scope**: Single page, single user (owner), no traffic concerns. Designed for personal use.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Static-First | ✅ PASS | Static HTML+CSS served from GitHub Pages. No backend, no API, no database. |
| II. Single Page | ✅ PASS | Exactly one page: `index.html`. No routing, no sub-pages. |
| III. Minimal Stack | ✅ PASS | HTML + CSS only. No frameworks, no npm, no build tools. JavaScript not used. |
| IV. Easy to Edit and Maintain | ✅ PASS | Content is directly editable in `index.html` with any text editor. No compilation. |
| V. Clean and Fast | ✅ PASS | 2 files served (HTML + CSS), zero external dependencies, responsive design. |

**Technical Constraints Check:**

| Constraint | Status | Notes |
|------------|--------|-------|
| Hosting: GitHub Pages | ✅ PASS | Deployed via git push to `main`. |
| Domain: czitrow.xyz | ✅ PASS | CNAME file included. |
| Max 3 files | ✅ PASS | `index.html`, `styles.css`, `CNAME` — exactly 3. |
| No external resources | ✅ PASS | All CSS local, no CDN, no Google Fonts. |
| Browser target: last 2 versions | ✅ PASS | Standard HTML5 + CSS3, no polyfills needed. |
| Responsive: 320px+ | ✅ PASS | CSS media queries for mobile and desktop. |

**No violations. No complexity justifications needed.**

## Project Structure

### Documentation (this feature)

```text
specs/001-czitrow-card/
├── spec.md              # Feature specification
├── plan.md              # This file
├── research.md          # Phase 0 output
├── data-model.md        # Phase 1 output
├── quickstart.md        # Phase 1 output
├── contracts/           # Phase 1 output (skipped — no external interfaces)
└── checklists/
    └── requirements.md  # Spec quality checklist
```

### Source Code (repository root)

```text
czitrow-card/
├── index.html           # Single page — all content lives here
├── styles.css           # All styles — dark theme, responsive
├── CNAME                # Custom domain: czitrow.xyz
├── .specify/            # Spec Kit configuration (already exists)
├── .speckit/            # Spec Kit Hermes commands (already exists)
├── specs/               # Feature specs and plans (already exists)
└── AGENTS.md            # Agent context (already exists)
```

**Structure Decision**: Single project, flat structure. No `src/`, no `tests/`, no build directory. This is a 3-file static site — the entire source code is at the repository root.

## Phase 0: Research

### Research Task 1: Color palette for dark minimal design

**Decision**: Use a dark palette with high contrast for readability.

- **Background**: `#0a0a0a` (near black) or `#111111` (dark gray)
- **Text**: `#e0e0e0` (light gray) — not pure white to reduce eye strain
- **Accent**: `#00d4aa` (teal/cyan) — for links and hover states, complements dark theme
- **Muted**: `#666666` — for secondary text like the footer

**Rationale**: High contrast ensures readability (WCAG AA compliance). Teal/cyan accent is distinctive without being garish. These colors work well on both small and large screens.

**Alternatives considered**:
- Purple accent (too common in dev portfolios)
- Blue accent (too corporate)
- Pure white text (too harsh on dark backgrounds, eye strain)

### Research Task 2: Typography for zero-dependency site

**Decision**: Use system font stack only.

```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

**Rationale**: No external fonts allowed (constitution constraint FR-007). System fonts render fast, look native on each platform, and require zero HTTP requests.

**Alternatives considered**:
- Google Fonts (rejected — external dependency violates FR-007)
- Self-hosted web fonts (rejected — adds file complexity, violates "max 3 files" constraint)

### Research Task 3: Responsive layout pattern for single-page card

**Decision**: CSS Flexbox, vertically centered, single column.

**Rationale**: A personal card page is naturally a single column of content (name → tagline → links → description → footer). Flexbox is the simplest layout method that handles vertical centering and responsive width without any framework.

**Alternatives considered**:
- CSS Grid (overkill for a single column)
- Bootstrap/tailwind (rejected — violates constitution, no frameworks)

### Research Task 4: GitHub Pages deployment with custom domain

**Decision**: Standard GitHub Pages setup with CNAME file.

**Rationale**: GitHub Pages natively supports custom domains. The `CNAME` file in the repo root tells GitHub which domain to serve. DNS is configured separately in Porkbun (already done per assumptions).

**Key steps**:
1. Push repo to GitHub
2. Enable GitHub Pages in repo settings (source: `main` branch, root)
3. `CNAME` file contains: `czitrow.xyz`
4. Porkbun DNS already points to GitHub Pages

**Alternatives considered**:
- Netlify/Vercel (rejected — adds complexity, constitution says GitHub Pages)
- GitHub Actions build pipeline (rejected — no build step needed)

**All NEEDS CLARIFICATION resolved. No unknowns remaining.**

## Phase 1: Design & Contracts

### Data Model

See [data-model.md](./data-model.md) for entity details.

### Contracts

**Skipped**: This is a static website with no external interfaces, no API, and no user input. There are no contracts to define. The "interface" is the visual page itself, documented in the spec and data model.

### Quickstart

See [quickstart.md](./quickstart.md) for local development and deployment instructions.

### Agent Context Update

Updated `AGENTS.md` to reference this plan file.