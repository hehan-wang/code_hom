# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website project that provides a Chinese-language setup guide for Claude Code CLI tool. The project consists of:

- `index.html` - Main webpage with interactive setup instructions for installing and configuring Claude Code
- `README.md` - Detailed setup guide in markdown format (Chinese)
- `netlify.toml` - Netlify deployment configuration

## Development

### Local Development
Open `index.html` directly in a browser to preview the website. No build process or development server is required.

### Deployment
The site is configured for Netlify deployment:
- Build command: `echo 'No build command needed'` (no build process)
- Publish directory: `.` (root directory)
- Redirects all routes to `/index.html` for SPA behavior

## Project Structure

This is a simple static website with no package.json, build tools, or dependencies. The entire functionality is contained within:

- HTML structure and content in `index.html`
- Embedded CSS styling (responsive design with mobile support)
- Embedded JavaScript for OS-specific installation tab switching
- Netlify configuration for hosting

## Code Conventions

- Uses semantic HTML5 structure
- CSS follows BEM-like naming conventions
- Responsive design with mobile-first approach
- Chinese language content with UTF-8 encoding
- Modern CSS features (Flexbox, CSS Grid, custom properties)