# Mona Mayhem — Agent Instructions

## Project Overview

A retro arcade-themed GitHub Contribution Battle Arena built with **Astro v5** (SSR). Users enter two GitHub usernames and the app compares their contribution graphs in a game-style UI.

- **Framework**: Astro v5 with `output: 'server'` (fully server-rendered, no static output)
- **Adapter**: `@astrojs/node` in standalone mode
- **Font**: Press Start 2P (retro gaming aesthetic — keep it)
- **API**: GitHub contribution graph data fetched server-side

## Key Files

| Path | Purpose |
|------|---------|
| `src/pages/index.astro` | Main page — the battle arena UI |
| `src/pages/api/contributions/[username].ts` | API route for GitHub contribution data |
| `astro.config.mjs` | Astro config — SSR + Node adapter |

## Build & Dev Commands

```bash
npm run dev       # Start dev server (http://localhost:4321)
npm run build     # Production build
npm run preview   # Preview production build locally
```

## Astro Conventions

- Pages live in `src/pages/`. File name = route (e.g. `src/pages/about.astro` → `/about`).
- API routes use TypeScript (`.ts`) and export named handlers: `GET`, `POST`, etc. Export `prerender = false` to keep them server-rendered.
- Use the frontmatter fences (`---`) in `.astro` files for server-side logic; everything below is the HTML template.
- Astro components (`.astro`) are not React — no hooks, no `useState`. Use vanilla JS `<script>` tags for client interactivity or add an integration (React, Svelte, etc.) if needed.
- `Astro.params` gives dynamic route params; `Astro.request` gives the raw Request object in SSR pages/endpoints.
- Styles can be scoped (`<style>`) inside `.astro` files — they are automatically scoped to the component.

## What to Build

The app is a workshop starting point. The core features to implement are:

1. **`GET /api/contributions/[username]`** — fetch and return GitHub contribution data for a given username.
2. **`src/pages/index.astro`** — battle arena UI: two username inputs, fetch both users' data, display a comparison.

> The `workshop/` directory contains the step-by-step guide but is not part of the app source. Ignore it when working on the application code.
