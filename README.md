# Astro site template

A minimal, dependency-light starter for a personal or small site built with
[Astro](https://astro.build). No UI framework, no CSS framework, just plain
`.astro` components and a Markdown blog.

## Getting started

```sh
npm install
npm run dev
```

Then open http://localhost:4321.

## Make it yours

1. Edit `src/site.config.ts`: name, tagline, brokerage, phone, email, areas.
2. Edit the four paragraphs in `src/copy/home.md`. Each one is a screen.
3. Replace the photos in `src/assets/`.
4. Set `site` in `astro.config.mjs` to the production URL.

## Project structure

```
src/
  assets/          hero.jpg (backdrop and social preview), portrait.jpg
  components/      Masthead (letterhead), Tile (photo + text), Closing, BaseHead
  copy/home.md     The four bio paragraphs, one per screen
  layouts/         BaseLayout wraps every page and runs the fade-up script
  pages/           index.astro and 404.astro
  styles/          Global CSS and design tokens
  site.config.ts   Name, tagline, brokerage, phone, email, areas
public/            Favicons and static files
```

## Commands

| Command           | Action                                  |
| ----------------- | --------------------------------------- |
| `npm run dev`     | Start dev server at `localhost:4321`    |
| `npm run build`   | Build production site to `./dist/`      |
| `npm run preview` | Preview the production build locally    |
| `npm run check`   | Type-check `.astro` files               |

## Deploying

The build output in `dist/` is fully static. Drop it on any static host
(Cloudflare Pages, Netlify, Vercel, GitHub Pages). See
https://docs.astro.build/en/guides/deploy/ for host-specific guides.

### Cloudflare Workers (Git integration)

`wrangler.jsonc` is already set up to serve `dist/` as static assets. In the
Cloudflare dashboard under **Workers & Pages → Create → Import a repository**,
use:

| Field           | Value                |
| --------------- | -------------------- |
| Build command   | `npm run build`      |
| Deploy command  | `npx wrangler deploy` |

Or deploy from your machine with `npm run deploy`.
