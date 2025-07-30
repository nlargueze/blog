# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal blog built with Zola, a fast static site generator written in Rust. The site is configured to be deployed at `https://blog.nicklabs.io`.

## Development Commands

### Building and Serving
- `zola build` - Build the site (deletes output directory and rebuilds)
- `zola serve` - Serve the site locally with auto-reload on changes
- `zola check` - Validate the project without rendering (checks links)

### Project Structure Validation
- `zola check` - Essential before deployment to catch broken links and validation errors

## Architecture

### Directory Structure
- `content/` - Markdown content files
  - `blog/` - Blog posts with `_index.md` for section configuration
- `templates/` - Tera template files
  - `base.html` - Base template with common structure
  - `blog.html` - Blog listing template  
  - `blog-page.html` - Individual blog post template
  - `index.html` - Homepage template
- `static/` - Static assets (CSS, images, etc.)
- `public/` - Generated site output (ignored in git)
- `config.toml` - Zola configuration

### Template System
Uses Tera templating engine with template inheritance:
- All templates extend `base.html`
- Blog section uses `blog.html` for listings and `blog-page.html` for individual posts
- Content is managed through frontmatter in markdown files

### Content Management
- Blog posts are markdown files in `content/blog/`
- Section configuration in `content/blog/_index.md` sets sorting by date
- Posts are sorted chronologically and listed automatically

## Configuration Notes

- Sass compilation is disabled
- Search indexing is disabled  
- Syntax highlighting is disabled
- Site is configured for deployment to `blog.nicklabs.io`