# Capri Auto Works

Live: https://www.capriautoworks.online/

One static page hosted by Vercel project `capri-auto-works`, deployed from GitHub `main`. No build step and no framework.

- `index.html`: all content, inline CSS and inline JS
- `assets/capri-logo.webp`, `assets/capri-logo.png`: logo (WebP for the page, PNG for the favicon)
- `assets/fonts/`: self-hosted Archivo and Big Shoulders (SIL OFL 1.1)
- `assets/og-image.jpg`: 1200×630 social share image
- `favicon.ico`, `apple-touch-icon.png`, `assets/app-icons/`, `site.webmanifest`: browser and home-screen icons (cropped from the logo's "C")
- `robots.txt`, `sitemap.xml`, `llms.txt`: search and AI-answer crawler entry points

Preview locally with `python3 -m http.server 4173`.

Release process and editorial rules: [docs/figma-workflow.md](docs/figma-workflow.md). Since v10, production no longer matches the Figma frames; see the v10 section there.
