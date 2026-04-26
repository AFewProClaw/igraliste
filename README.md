# Igralište 🛝

One-page playground website built with [Astro](https://astro.build) and [Tailwind CSS](https://tailwindcss.com).

Live: https://igraliste.afew.pro

## Stack

- **Framework:** AstroJS (static output)
- **Styling:** Tailwind CSS v4
- **Serving:** `serve` (static file server in Docker)
- **CI/CD:** GitHub Actions → GHCR → server deploy

## Local dev

```bash
npm install
npm run dev
```

Open http://localhost:4321

## Build

```bash
npm run build
```

Output goes to `dist/`.

## Deploy

Push to `main` — GitHub Actions builds the Docker image, pushes to GHCR, and deploys to the server automatically.

## Environment variables

None required (fully static site).
