# Quickstart: Czitrow Card

**Feature**: 001-czitrow-card | **Date**: 2026-05-10

## Prerequisites

- A text editor (any: VS Code, nano, Notepad, etc.)
- A web browser
- Git (for version control and deployment)
- A GitHub account
- A Porkbun account (for DNS, already configured per assumptions)

## Local Development

### 1. Clone the repository

```bash
git clone <repo-url> czitrow-card
cd czitrow-card
```

### 2. Open the site locally

Simply open `index.html` in your browser:

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

That's it. No server needed. No build step. No `npm install`. Just open the file.

### 3. Make changes

Edit `index.html` to change content (name, tagline, links, description, footer).
Edit `styles.css` to change visual styles (colors, fonts, spacing, layout).

### 4. Verify changes

Refresh the browser after saving. Check:
- Content is readable
- Links work and open in new tabs
- Layout looks good on mobile and desktop (resize browser window)
- No external resources loaded (check DevTools Network tab)

### 5. Commit and deploy

```bash
git add .
git commit -m "describe your change"
git push origin main
```

GitHub Pages will automatically deploy on push to `main`. Changes appear at `czitrow.xyz` within 1-5 minutes.

## File Reference

| File | Purpose | Edit? |
|------|---------|-------|
| `index.html` | All page content | Yes — change text, links, structure |
| `styles.css` | All visual styles | Yes — change colors, fonts, spacing |
| `CNAME` | Custom domain config | No — leave as `czitrow.xyz` |
| `.specify/` | Spec Kit config | No — project management files |
| `.speckit/` | Spec Kit commands | No — project management files |
| `specs/` | Feature specs & plans | No — project management files |

## Deployment Checklist

- [ ] `CNAME` file contains `czitrow.xyz`
- [ ] GitHub Pages enabled in repo settings (source: `main`, root)
- [ ] Porkbun DNS points to GitHub Pages (already configured)
- [ ] Push to `main` triggers deployment
- [ ] Site accessible at `https://czitrow.xyz` within 5 minutes