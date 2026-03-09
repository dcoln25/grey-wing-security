# Grey Wing Security Website

Company website for Grey Wing Security, LLC — [greywingsec.com](https://greywingsec.com)

## Tech Stack

- **Static site generator:** Hugo
- **Theme:** Blowfish (git submodule at `themes/blowfish/`)
- **Hosting:** GitHub Pages with custom domain
- **Deployment:** GitHub Actions (`.github/workflows/deploy.yml`)
- **Contact form:** Formsubmit.co (no backend required)

## Project Structure

```
config/_default/          # Hugo configuration
  hugo.toml               # Base config (baseURL, theme, taxonomies)
  languages.en.toml       # Site title, description, author, logo path
  menus.en.toml           # Main nav and footer menu items
  params.toml             # Theme params (color scheme, layout, article settings)
  markup.toml             # Markdown rendering settings

content/                  # Site pages (Markdown)
  _index.md               # Homepage (hero, service cards, "Why" section)
  about/index.md          # About page
  services/index.md       # Services (Managed Security, Incident Response, Compliance, IT Engineering)
  contact/index.md        # Contact page (email, LinkedIn, Formsubmit.co form)
  blog/_index.md          # Blog listing page
  blog/*/index.md         # Individual blog posts (each in its own folder)

assets/
  css/custom.css          # All custom CSS overrides (dark theme, mobile fixes, service cards, contact form)
  img/logo.svg            # Company logo (SVG)
  img/icon-*.svg          # Service card icons

static/                   # Files served as-is at site root
  CNAME                   # Custom domain (greywingsec.com)
  og-image.png            # Social media preview image (1200x630)
  favicon-*.png           # Favicons (16x16, 32x32)
  apple-touch-icon.png    # Apple touch icon
  android-chrome-512x512.png
  img/icon-*.svg          # Service card icons (copied from assets for <img> tags)

layouts/
  partials/extend-head.html  # Forces dark mode, clears stale localStorage light mode preference
```

## Key Configuration

- **Color scheme:** Ocean (`config/_default/params.toml`)
- **Dark mode only:** `defaultAppearance = "dark"`, `autoSwitchAppearance = false`, appearance switcher disabled
- **Pure black background:** CSS overrides `--color-neutral-900: 0, 0, 0` and `--color-neutral-800: 10, 10, 10` in `assets/css/custom.css`
- **Homepage layout:** Hero (`homepage.layout = "hero"`)
- **Pagination arrows:** Disabled (`article.showPagination = false`)

## Adding a Blog Post

Create a new folder in `content/blog/` with an `index.md` file:

```
content/blog/my-new-post/
  index.md
```

Front matter template:
```yaml
---
title: "Post Title"
date: 2026-03-08
description: "Brief description for previews and SEO."
tags: ["cybersecurity", "compliance"]
categories: ["insights"]
---
```

## Local Development

```bash
hugo server -D
```

## DNS

Custom domain `greywingsec.com` via Cloudflare — A records for apex + CNAME for www, both DNS-only (grey cloud).
