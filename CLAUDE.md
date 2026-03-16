# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with this repository.

## Project Overview

This repository contains a personal blog built with Hugo, using the Typo theme as a git submodule under `themes/typo/`.

## Key Configuration

- **Base URL**: `https://blog.xlau.uk/`
- **Main config**: `config.toml`
- **Theme**: `themes/typo/`
- **Primary build script**: `build.sh`
- **Cloudflare config**: `wrangler.toml`
- **GitHub Pages workflow**: `.github/workflows/hugo.yaml`

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

# Build locally
hugo

# Production-style build
hugo --gc --minify --environment production
```

## Content Structure

- **Home page intro and site-wide navigation**: `config.toml`
- **Blog posts**: `content/posts/[year]/...`
- **About page**: `content/about/`
- **Images and static assets**: `content/imgs/` and `content/`

## Architecture Notes

- The site uses Hugo extended.
- `themes/typo/layouts/_default/home.html` renders the intro block and the social icon row.
- The Typo theme already contains SVG support for `email`, `twitter`, and `github`.
- `build.sh` is the Cloudflare-oriented build entrypoint and installs Hugo, Go, Dart Sass, and Node.js before running `hugo build --gc --minify`.
- `.github/workflows/hugo.yaml` is still present for GitHub Pages deployment and currently pins Hugo `0.134.2`.

## Editing Guidance

- Prefer changing site-level behavior in `config.toml` before editing the theme.
- Treat `themes/typo/` as a maintained theme submodule; avoid unnecessary theme edits for simple content or configuration changes.
- When changing home page social links, verify with a local `hugo` build.
