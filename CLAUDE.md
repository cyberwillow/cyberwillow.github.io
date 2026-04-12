# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

CyberWillow is a static HTML/CSS personal security blog with no build tools, frameworks, or dependencies. Open any `.html` file directly in a browser to preview. There is no build step.

## Site Structure

- `index.html` — Blog homepage with hero, post cards grid, newsletter section, and footer
- `about.html` — About page with two-column layout (identity left, bio/content right)
- `post-template.html` — Template to duplicate when creating new posts
- `style.css` — Single stylesheet for the entire site (all components)
- `posts/` — (expected) directory for individual post HTML files

## Adding a New Post

1. Duplicate `post-template.html` into `posts/your-post-slug.html`
2. Update `<title>`, the `post-header` section (date, read time, tag, title, subtitle, topics)
3. Write content inside `<article class="post-body">` using the supported elements documented in the template header comment
4. Add a new `<article class="post">` card to the top of `.posts__grid` in `index.html` — follow the pattern in the existing cards

## Post Tag Color Classes

Tags on cards and post headers use these CSS classes for color:
- `post__tag--threat` — orange/red (Threat Research)
- `post__tag--detect` — blue (Detection Engineering)
- `post__tag--cloud` — purple (Cloud Security)
- `post__tag--thought` — gold (Perspective)

## CSS Architecture

`style.css` uses BEM naming (`.block__element--modifier`) and CSS custom properties defined in `:root`. All layout uses CSS Grid and Flexbox. Key tokens:

- `--c-accent: #6db882` — sage green, the primary brand color
- `--f-display` / `--f-body` / `--f-mono` — the three font stacks
- `--w-content: 1120px` / `--w-narrow: 780px` — layout width constraints

The stylesheet is organized top-to-bottom by component in the same order they appear on the page.

## Items to Personalize

The `about.html` has placeholder values that need updating:
- Avatar SVG placeholder → replace with `<img src="your-photo.jpg">`
- `https://github.com/cyberwillow` → actual GitHub URL
- `https://www.linkedin.com/in/hunter-e-schwartz/` — LinkedIn (filled in)
- `mailto:hunter@cyberwillow.com` — Email (filled in)
