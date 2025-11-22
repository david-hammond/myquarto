# Claude-Themed Documentation Template

A professional Quarto website template with Claude AI's warm, inviting design aesthetic.

## Features

- 🎨 **Claude AI Color Palette**: Warm orange (#C15F3C) accents with pure white backgrounds
- 🏢 **Dual Branding**: Client logo in navbar, organization logo in top-right
- 📱 **Responsive Sidebar Navigation**: Clean, collapsible sidebar menu
- 📄 **Pre-built Pages**: Getting Started, Documentation, Tutorials, API Reference, Blog, and About
- ♿ **Accessible**: WCAG AA compliant color contrasts
- 🚀 **Ready to Deploy**: Works with Quarto Pub, Netlify, GitHub Pages

## Quick Start

### Install Template

```bash
quarto use template yourusername/mydocstemplate
```

When prompted, enter your project name (e.g., `my-docs`). This creates a new directory with all template files.

### Customize

1. **Add Your Logos**
   - Replace `client-logo.png` with your client's logo
   - Replace `my-logo.png` with your organization logo

2. **Update Site Configuration**

   Edit `_quarto.yml`:
   ```yaml
   website:
     title: "Your Site Title"
   ```

3. **Customize Content**
   - Edit the existing `.qmd` files with your content
   - Add new pages as needed

### Preview

```bash
quarto preview
```

### Publish

```bash
quarto publish netlify
# or
quarto publish gh-pages
# or
quarto publish quarto-pub
```

## Project Structure

```
mydocstemplate/
├── _quarto.yml              # Site configuration
├── template.qmd             # Template landing page (auto-renamed)
├── index.qmd                # Home page
├── getting-started.qmd      # Getting started guide
├── documentation.qmd        # Documentation overview
├── tutorials.qmd            # Tutorials section
├── api-reference.qmd        # API reference
├── blog.qmd                 # Blog/updates
├── about.qmd                # About page
├── styles.css               # Quarto.org base styles
├── claude-theme.scss        # Claude AI color theme
├── client-logo.png          # Client logo
└── my-logo.png              # Organization logo
```

## Customization

### Color Scheme

The Claude theme uses:
- Primary: #C15F3C (warm orange)
- Background: #F4F3EE (cream)
- Content: #FFFFFF (white panels)
- Text: #2C2C2C (dark gray)

Modify `claude-theme.scss` to adjust colors.

### Navigation

Edit the sidebar in `_quarto.yml`:

```yaml
sidebar:
  contents:
    - text: "Your Page"
      href: your-page.qmd
    - section: "Your Section"
      contents:
        - href: page1.qmd
          text: Page 1
```

### Footer

Update footer content in `_quarto.yml`:

```yaml
page-footer:
  left: "Powered by [Your Organization](https://yoursite.com)"
navbar:
  right:
    - text: |
        <img src="my-logo.png" style="height: 30px; vertical-align: middle;" alt="My Logo">
      href: "https://yoursite.com"
```

## Requirements

- Quarto 1.3 or higher

## License

This template is free to use and modify for your projects.

## Support

For issues or questions:
- Open an issue on GitHub
- Check Quarto documentation: https://quarto.org

---

Built with ❤️ using [Quarto](https://quarto.org)
