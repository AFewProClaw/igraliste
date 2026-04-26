# CLAUDE.md — Igralište

## What it is
One-page playground (igrište = "playground" in Croatian/Bosnian/Serbian) marketing site.

## Stack
- **AstroJS** (minimal template, static output)
- **Tailwind CSS v4** (via `@tailwindcss/vite` plugin)
- **No JS framework** — pure Astro + HTML
- **Fonts:** Fredoka (headings), Inter (body) via Google Fonts

## Structure
```
src/
  pages/index.astro   — the entire site (single page)
  styles/global.css   — Tailwind imports
astro.config.mjs      — Astro config with Tailwind vite plugin
Dockerfile            — builder (npm build) + runner (serve static)
```

## Build
```bash
npm install
npm run build    # outputs to dist/
npm run dev      # dev server at localhost:4321
```

## Deploy
CI/CD via `.github/workflows/deploy.yml`. Push to `main` → Docker image to GHCR → pulled by server at `/opt/apps/igraliste/`.

## Server
- **Port:** 3114 (host) → 3000 (container)
- **URL:** https://igraliste.afew.pro
- **Access:** Public (no Cloudflare Access policy)

## Notes
- All content is in `src/pages/index.astro` — inline Astro component map loops for the feature grid and testimonials.
- Tailwind v4 config is zero-config (no `tailwind.config.*` file needed).
