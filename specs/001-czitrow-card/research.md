# Research: Czitrow Card

**Feature**: 001-czitrow-card | **Date**: 2026-05-10

## Research Task 1: Color palette for dark minimal design

**Decision**: Dark palette with teal/cyan accent for links.

| Element | Color | Hex |
|---------|-------|-----|
| Background | Near black | `#0a0a0a` |
| Primary text | Light gray | `#e0e0e0` |
| Accent (links, hover) | Teal/Cyan | `#00d4aa` |
| Secondary text (footer, muted) | Medium gray | `#666666` |

**Rationale**: High contrast for readability (WCAG AA). Teal is distinctive without being garish. Works well on all screen sizes.

**Alternatives considered**:
- Purple accent — too common in dev portfolios
- Blue accent — too corporate
- Pure white text — too harsh, causes eye strain on dark backgrounds

---

## Research Task 2: Typography for zero-dependency site

**Decision**: System font stack only.

```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

**Rationale**: No external fonts allowed (FR-007). System fonts render fast, look native, zero HTTP requests.

**Alternatives considered**:
- Google Fonts — rejected (external dependency violates FR-007)
- Self-hosted web fonts — rejected (adds file, violates "max 3 files" constraint)

---

## Research Task 3: Responsive layout for single-page card

**Decision**: CSS Flexbox, single column, vertically centered.

**Rationale**: A personal card is naturally single-column content. Flexbox handles vertical centering and responsive width without any framework.

**Layout structure**:
- Body: flex, center both axes, min-height 100vh
- Container: max-width ~600px, padding, centered
- Name: large heading
- Tagline: smaller text below name
- Links: vertical or horizontal list with spacing
- Description: paragraph with secondary styling
- Footer: small muted text at bottom

**Alternatives considered**:
- CSS Grid — overkill for single column
- Bootstrap/Tailwind — rejected (violates constitution, no frameworks)

---

## Research Task 4: GitHub Pages deployment with custom domain

**Decision**: Standard GitHub Pages with CNAME file.

**Steps**:
1. Push repo to GitHub
2. Enable GitHub Pages in repo settings (source: `main` branch, `/` root)
3. `CNAME` file contains: `czitrow.xyz`
4. DNS at Porkbun already points to GitHub Pages (per assumption)

**Alternatives considered**:
- Netlify/Vercel — rejected (adds complexity, constitution says GitHub Pages)
- GitHub Actions pipeline — rejected (no build step needed)

---

## Summary

All research questions resolved. No external dependencies needed. No frameworks needed. The implementation is purely HTML + CSS with system fonts and a hand-crafted dark color palette.