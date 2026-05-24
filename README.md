# Speten Consulting Group — Website

Static site for [spetenconsulting.com](mailto:shane@spetenconsulting.com), deployed via GitHub Pages (Jekyll).

## Structure

```
_config.yml              Jekyll site config
_layouts/default.html    Shared shell — <head>, nav, footer
index.html               Home (front matter + page body only)
about.html               About Shane
services.html            Four services with anchors (#fractional-cpo, etc.)
contact.html             Email, phone, what to expect
css/style.css            Shared stylesheet — palette and typography
```

Each page file starts with a YAML front matter block:

```
---
layout: default
nav: about
title: "About | Speten Consulting Group"
description: "..."
---
```

The `nav` value (home/about/services/contact) tells the layout which nav link to highlight.

## To edit something everywhere

- **Nav / footer / fonts / `<head>`** → `_layouts/default.html`
- **Colors / typography** → CSS variables at the top of `css/style.css`
- **A single page's body** → that page's `.html` file (front matter + content)

## Local preview

Plain browser open works for the body content, but the layout won't render without Jekyll. To preview the full site locally:

```
gem install bundler jekyll
bundle init
bundle add jekyll
bundle exec jekyll serve
```

Then visit `http://localhost:4000`.

GitHub Pages renders Jekyll automatically on push — no action needed for production.
