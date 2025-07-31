# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Mad Monkey Club website - a landing page for tech leadership consulting services. It's built with Astro and uses Tailwind CSS v4 for styling. The site is deployed using Docker with nginx serving the static files.

## Commands

| Command | Purpose |
|---------|---------|
| `npm run dev` | Start development server at localhost:4321 |
| `npm run build` | Build production site to ./dist/ |
| `npm run preview` | Preview production build locally |
| `npm run astro` | Run Astro CLI commands |

## Architecture

- **Framework**: Astro with static site generation
- **Styling**: Tailwind CSS v4 via Vite plugin
- **Deployment**: Multi-stage Docker build with nginx
- **Structure**: Component-based architecture with layouts and reusable components
- **Styles**: Global CSS imports Tailwind at `src/styles/global.css`

## Project Structure

```
src/
├── components/     # Reusable UI components
│   ├── Hero.astro
│   ├── ServiceCard.astro
│   ├── ProjectCard.astro
│   └── Footer.astro
├── layouts/        # Page layouts
│   └── BaseLayout.astro
├── pages/          # Route-based pages
│   └── index.astro
└── styles/         # Global styles
    └── global.css
```

## Key Files

- `src/layouts/BaseLayout.astro` - Base HTML layout with head metadata
- `src/pages/index.astro` - Main landing page using components
- `src/components/*.astro` - Reusable UI components with TypeScript props
- `astro.config.mjs` - Astro configuration with Tailwind CSS Vite plugin
- `Dockerfile` - Multi-stage build (deps → builder → nginx runtime)
- `nginx.conf` - nginx configuration for serving static files

## Development Notes

- Uses Tailwind CSS v4 via `@tailwindcss/vite` plugin (recommended approach for v4)
- Component-based architecture with TypeScript interfaces for props
- Static assets go in `public/` directory
- Single-page application with anchor links for navigation