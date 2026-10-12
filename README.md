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

1. Edit `src/site.config.ts`: title, description, author, nav, social links.
2. Set `site` in `astro.config.mjs` to your production URL.
3. Replace the copy in `src/pages/index.astro`, `about.astro`, and `contact.astro`.
4. Add posts to `src/content/blog/` as Markdown files (see `hello-world.md`).
5. Swap `public/favicon.svg` and `public/favicon.ico`.
6. Tweak colors and fonts in `src/styles/global.css`.

## Project structure

```
src/
  components/      Header, Footer, BaseHead (meta tags)
  content/blog/    Markdown posts
  content.config.ts  Blog collection schema
  layouts/         BaseLayout wraps every page
  pages/           File-based routes
  styles/          Global CSS
  site.config.ts   Site-wide settings
public/            Static assets served as-is
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
