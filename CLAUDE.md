# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal blog website built with the Hugo static site generator, using a custom fork of the Typo theme. The blog is hosted on GitHub Pages and deployed via GitHub Actions.

## Key Configuration

- **Base URL**: https://kylexlau.github.io/
- **Config File**: `config.toml` - Hugo configuration with theme settings, menus, and markup options
- **Theme**: Custom fork of Typo theme at `themes/typo/` (Git submodule)
- **Deployment**: GitHub Actions workflow at `.github/workflows/hugo.yaml`

## Common Development Commands

```bash
# Clone with submodules
git clone --recurse-submodules git@github.com:kylexlau/kylexlau.github.io.git

# Initialize submodules if already cloned
git submodule update --init --recursive

# Preview locally
hugo server

# Preview with drafts
hugo server -D

# Build for production
hugo --gc --minify --environment production
```

## Content Structure

- **Blog Posts**: `content/posts/[year]/[month]-[day]-[slug].md` - Markdown files with YAML front matter
- **Images**: `content/imgs/` - Image assets for posts
- **About Page**: `content/about/` - Static about page

## Post Front Matter Example

```yaml
---
title: "Post Title"
date: "2024-01-01"
toc: true
autonumber: true
readTime: false
draft: false
math: false
---
```

## Architecture Notes

- The site is built with Hugo extended version (currently v0.134.2)
- Uses Dart Sass for SCSS compilation
- Deploys automatically to GitHub Pages on pushes to master
- Production output goes to `public/` (gitignored)
- Theme is a Git submodule pointing to `git@github.com:kylexlau/typo.git`
