# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Quarto website template designed with Claude AI's warm, inviting aesthetic. It provides a documentation site template with dual branding support (client logo + organization logo), Claude-inspired color theming, and optimized layout for professional documentation.

## Core Commands

### Development
```bash
# Preview the site locally (serves on http://localhost:4200)
quarto preview

# Render the site without serving
quarto render
```

### Publishing
```bash
# Deploy to various platforms
quarto publish netlify
quarto publish gh-pages
quarto publish quarto-pub
```

## Architecture

### Theming System

The template uses a two-layer styling approach:

1. **styles.css** - Base styles adapted from quarto.org, providing foundational responsive layout, navigation behavior, and component styling. Contains navbar behavior, link card layouts, carousel components, and media queries for responsive design.

2. **claude-theme.scss** - Claude AI color palette and theme overrides applied on top of base styles. Key principle: **pure white backgrounds throughout** with warm orange (#C15F3C) accents. This file enforces the "no grey borders" design philosophy by explicitly setting borders to transparent/none globally.
   - **Note**: This file was recently removed from the repository. If you need to add theme customization, recreate it in the root directory and ensure it's referenced in `_quarto.yml` under `format.html.css`.

### Configuration Structure

**_quarto.yml** is the central configuration file controlling:
- Site metadata and title
- Navbar configuration (dual logo placement: client logo on left, organization logo on right)
- Sidebar navigation structure
- Grid layout dimensions (sidebar: 280px, body: 1000px, margin: 250px, gutter: 3rem)
- Theme cascade: cosmo base → styles.css → claude-theme.scss (when present)

### Content Files

- **template.qmd** - Template landing page for new installations (gets auto-renamed by Quarto template system)
- **index.qmd** - Actual home page for the documentation site
- **customization.qmd** - Instructions for updating logos, titles, navigation
- **styling.qmd** - Instructions for changing colors and appearance

## Key Design Principles

### Pure White Aesthetic
All backgrounds default to #FFFFFF (white), not cream or grey. The SCSS (when present) enforces this globally on body, navbar, sidebar, main content, and footer. Any grey borders are explicitly removed.

### Dual Branding
- Client logo: `images/client-logo.png` in navbar left (referenced in `_quarto.yml` as `navbar.logo`)
- Organization logo: `images/my-logo.png` in navbar right (embedded as img tag in `navbar.right` YAML section)

### Layout Spacing
The template reduces gaps between navbar and content (padding-top: 1.5rem) for a tighter, more compact feel compared to Quarto defaults.

### Color Palette
- Primary: #C15F3C (Claude warm orange)
- Links, active states, and accents use this orange
- Code blocks use dark background (#2C2C2C) with light text
- Inline code uses subtle light background (#F8F7F5)

## Common Customization Tasks

### Update Site Title
Edit `_quarto.yml`:
```yaml
website:
  title: "Your New Title"
```

### Add/Remove Navigation Items
Edit sidebar contents in `_quarto.yml`:
```yaml
sidebar:
  contents:
    - text: "Page Name"
      href: pagename.qmd
```

### Replace Logos
Replace the files in the `images/` directory:
- `images/client-logo.png` - Client logo (appears in navbar left)
- `images/my-logo.png` - Organization logo (appears in navbar right)
PNG recommended, ~30-36px height works well.

### Change Primary Color
If `claude-theme.scss` exists, edit the `$claude-orange` variable and adjust dependent colors as needed. If the file doesn't exist, you'll need to recreate it and add it to the CSS cascade in `_quarto.yml`.

### Add New Pages
1. Create `.qmd` files in root directory
2. Add references in `_quarto.yml` sidebar configuration

### Adjust Grid Layout
Edit `_quarto.yml` under `format.html.grid`:
```yaml
format:
  html:
    grid:
      sidebar-width: 280px
      body-width: 1000px
      margin-width: 250px
      gutter-width: 3rem
```

## Current Design Improvement Goals

See `improvements.md` for ongoing design refinement ideas:
- Pure white aesthetic (removing all grey borders and backgrounds)
- Pinned navbar that stays visible during scroll (AWS docs-style)
- More efficient use of horizontal space (better content/TOC balance)
- Removal of GitHub links from footer
- Organization logo always visible in top-right
