# Feature Specification: Czitrow Card

**Feature Branch**: `001-czitrow-card`  
**Created**: 2026-05-10  
**Status**: Draft  
**Input**: User description: "A minimal single-page personal card website for czitrow.xyz, deployed on GitHub Pages. Shows name, a short tagline, 3 links, a brief description, and a footer. Static HTML+CSS only, no framework, no build step."

## User Scenarios & Testing

### User Story 1 - Visitor lands on the page (Priority: P1)

A visitor types `czitrow.xyz` into their browser and sees the owner's name, tagline, links, and description on a single, cleanly designed page.

**Why this priority**: This is the entire product. Without a visible, readable page, nothing else matters.

**Independent Test**: Open `index.html` in a browser. The page renders with name, tagline, links, and footer visible. Delivers the core value immediately.

**Acceptance Scenarios**:

1. **Given** a deployed site at `czitrow.xyz`, **When** a visitor navigates to the URL, **Then** they see the page title, name, tagline, 3 links, a description, and a footer — all on one page without scrolling errors or broken layout.
2. **Given** a visitor on a mobile device (320px+), **When** they open `czitrow.xyz`, **Then** all content is readable and nothing overflows or is cut off.

---

### User Story 2 - Owner edits content (Priority: P2)

The site owner opens `index.html` in any text editor, finds the content section, changes the tagline or a link, saves, and sees the change reflected on the page.

**Why this priority**: The site must be trivially editable. This validates the "easy to edit" principle from the constitution. Without this, maintenance becomes a burden.

**Independent Test**: Open `index.html` in a plain text editor, change the tagline text, save, open in browser. The change is reflected.

**Acceptance Scenarios**:

1. **Given** `index.html` opened in a text editor, **When** the owner changes the tagline text, **Then** the page reflects the new tagline after saving and reloading.
2. **Given** `index.html` opened in a text editor, **When** the owner changes a link URL or label, **Then** the link points to the new destination after saving and reloading.

---

### User Story 3 - Site loads fast with no dependencies (Priority: P3)

A visitor on a slow connection opens `czitrow.xyz` and sees the complete page load within 2 seconds, with no external resource requests.

**Why this priority**: Performance and zero-dependency are constitutional principles. Validating this ensures the site meets its own standards.

**Independent Test**: Open browser DevTools Network tab, load the page, confirm only `index.html` and `styles.css` are requested, and total load time is under 2 seconds on a normal connection.

**Acceptance Scenarios**:

1. **Given** a browser with DevTools open, **When** the page loads, **Then** only `index.html` and `styles.css` appear in the Network tab — no external fonts, scripts, or CDN requests.
2. **Given** a browser on a normal connection, **When** the page loads, **Then** the full page renders in under 2 seconds.

---

### Edge Cases

- What happens when a link target is unreachable? → The link still appears and is clickable; browser shows its standard error. No custom handling needed.
- What happens on very small screens (below 320px)? → Content may scroll but must not overflow or break layout.
- What happens if `CNAME` is misconfigured? → GitHub Pages serves from the default `.github.io` subdomain, which is acceptable as a fallback.

## Requirements

### Functional Requirements

- **FR-001**: The site MUST display a prominent name or alias of the site owner.
- **FR-002**: The site MUST display a short tagline below the name (one sentence).
- **FR-003**: The site MUST display exactly 3 clickable links with visible labels.
- **FR-004**: The site MUST display a brief "about this site" description section (1-3 sentences).
- **FR-005**: The site MUST display a footer with the domain name and current year.
- **FR-006**: The page MUST render correctly on screens from 320px wide upward.
- **FR-007**: The page MUST load with zero external resource requests (no CDN, no external fonts, no third-party scripts).
- **FR-008**: The site MUST be deployable on GitHub Pages with a custom domain via `CNAME` file.
- **FR-009**: The content MUST be editable by opening `index.html` in any plain text editor and changing text directly.
- **FR-010**: The page MUST use a dark color scheme (dark background, light text) with a minimalist aesthetic.
- **FR-011**: All 3 links MUST open in a new browser tab (target="_blank") so the visitor does not leave the page.
- **FR-012**: All visible content on the page (name, tagline, links, description, footer) MUST be written in Spanish.
- **FR-013**: The page MUST display the owner's real name: "William Ortiz".

### Key Entities

- **Page**: The single HTML document containing all content.
- **Link**: A labeled hyperlink pointing to an external URL. Exactly 3 instances on the page.
- **Footer**: Domain name and year, rendered at the bottom of the page.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A first-time visitor can identify the site owner's name, understand what the site is about, and access all 3 links within 5 seconds of landing.
- **SC-002**: The site owner can change the tagline or a link in under 1 minute using only a text editor.
- **SC-003**: The page loads completely with only 2 HTTP requests (HTML + CSS) and zero external dependencies.
- **SC-004**: The page renders correctly on mobile (320px), tablet (768px), and desktop (1440px) viewports.

## Clarifications

### Session 2026-05-10

- Q: What visual style do you want for the page? → A: Dark — dark background, light text, minimalist "terminal" or subtle "cyberpunk" aesthetic
- Q: How should the 3 links open? → A: In a new tab (target="_blank") so visitors don't lose the page
- Q: What language should the page content be in? → A: Spanish — all visible content in Spanish
- Q: What name/alias should be displayed on the page? → A: Real name — "William Ortiz"

## Assumptions

- The site owner (William) will display his real name "William Ortiz" on the page; the exact tagline text, link URLs, and description text will be provided.
- GitHub Pages is the target hosting platform; no other hosting is considered.
- The custom domain `czitrow.xyz` is already configured in Porkbun DNS pointing to GitHub Pages.
- Content language is Spanish for all visible text on the page.
- No analytics, SEO optimization, or social media metadata is required for v1.
- The site has a single page; no sub-pages or routing is in scope.