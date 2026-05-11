# Data Model: Czitrow Card

**Feature**: 001-czitrow-card | **Date**: 2026-05-10

## Overview

This is a static website with no database, no API, and no user input. The "data model" describes the logical structure of content within the single HTML file. There are no runtime entities — only static content elements embedded in `index.html`.

## Entities

### Page

The single HTML document that contains all content.

| Field | Type | Description |
|-------|------|-------------|
| title | text | Browser tab title: "William Ortiz" |
| lang | text | HTML lang attribute: "es" |
| charset | text | Character encoding: "utf-8" |
| viewport | text | Responsive meta tag: "width=device-width, initial-scale=1.0" |
| description | text | Meta description for SEO (future use, optional for v1) |

**Notes**: Exactly one Page entity. It is the entire site.

---

### Name (Hero Section)

The prominent display of the owner's name at the top of the page.

| Field | Type | Description |
|-------|------|-------------|
| text | text | "William Ortiz" (fixed) |
| element | HTML | `<h1>` heading |
| style | CSS | Large, bold, light color on dark background |

**Validation**: FR-001, FR-013

---

### Tagline

A short phrase below the name.

| Field | Type | Description |
|-------|------|-------------|
| text | text | To be provided by owner (one sentence, in Spanish) |
| element | HTML | `<p>` or `<h2>` with subtitle styling |
| style | CSS | Smaller than name, muted color |

**Validation**: FR-002, FR-012

---

### Link

A labeled hyperlink pointing to an external URL. Exactly 3 instances on the page.

| Field | Type | Description |
|-------|------|-------------|
| label | text | Visible text for the link (in Spanish) |
| url | URL | Destination URL |
| target | text | "_blank" (opens in new tab) |
| rel | text | "noopener noreferrer" (security best practice for target="_blank") |
| element | HTML | `<a>` inside a `<nav>` or `<ul>` |

**Validation**: FR-003, FR-011

**Constraints**:
- Exactly 3 links on the page
- All open in new tab (target="_blank" + rel="noopener noreferrer")
- Link URLs and labels to be provided by owner

---

### Description

A brief "about this site" section.

| Field | Type | Description |
|-------|------|-------------|
| text | text | 1-3 sentences in Spanish, to be provided by owner |
| element | HTML | `<p>` with secondary styling |
| style | CSS | Regular body text size, muted color |

**Validation**: FR-004, FR-012

---

### Footer

Domain name and year at the bottom of the page.

| Field | Type | Description |
|-------|------|-------------|
| domain | text | "czitrow.xyz" (fixed) |
| year | text | Current year (e.g., "2026") |
| separator | text | "·" or " — " between domain and year |
| element | HTML | `<footer>` element |
| style | CSS | Small text, muted color, centered |

**Validation**: FR-005

---

## Relationships

```text
Page (root)
├── Name (hero)
├── Tagline (below name)
├── Links (3x, inside nav)
├── Description (paragraph)
└── Footer (bottom)
```

All entities are children of the Page. There are no relational dependencies — each entity is independently editable in `index.html`.

## State Transitions

None. This is a static page with no interactive state. Content is changed by editing the HTML file directly.