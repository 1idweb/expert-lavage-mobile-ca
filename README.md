# expert-lavage-mobile

Static website for **expert-lavage-mobile.ca** — HTML + Tailwind CSS v4, hosted on GitHub Pages.

## Local development

```zsh
# 1. Install dependencies (once)
npm install

# 2. Build the CSS, then start Tailwind in watch mode + the local server
npm run dev
# → http://localhost:8081      (FR)
# → http://localhost:8081/en/  (EN)
```

Port 8081 is used on purpose to avoid clashing with other local projects on 8080.

## Scripts

| Command | Description |
|---|---|
| `npm run dev` | Build CSS, then watch CSS + serve `public/` on port 8081 |
| `npm run build` | Production build (minified CSS) — also run by GitHub Actions |
| `npm run css:build` | One-off unminified CSS build |

## Structure

- `src/styles.css` — Tailwind entry point; partials in `src/styles/` (`theme`, `base`, `components`)
- `public/` — the published site root (`index.html`, `en/index.html`, `CNAME`, `robots.txt`, `sitemap.xml`)
- `public/assets/style.css` — generated, **not committed**
- `.github/workflows/pages.yml` — builds and deploys `public/` on every push to `main`

## Deployment

In GitHub → Settings → Pages, set **Source: GitHub Actions**. DNS at WHC.ca points to GitHub Pages (see the A / CNAME records in the project notes).
