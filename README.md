# Astro Scholar

An academic website template built with [Astro](https://astro.build). Pages for publications, presentations, and a blog — all editable as plain files.

## Getting started

**The fastest path** is to fork this repo, edit the files listed below, and push to GitHub. The site deploys automatically to GitHub Pages — no local setup needed.

If you want to preview or build locally, you'll need [Node.js 18+](https://nodejs.org/en/download):

```bash
npm install
npm run dev        # http://localhost:4321
```

## What to change

### 1. Your details — `src/constants.ts`

Name, tagline, and social links. Set any field to `""` to hide it.

### 2. Portrait — `src/assets/portrait.png`

Replace with your own photo. Ideally square, 400×400px or larger.

### 3. Pages — `src/pages/`

Each `.astro` file is a page. Edit them directly:

- `index.astro` — homepage
- `about.astro` — bio, positions, education, awards
- `publications.astro` — the filter UI (data is in `src/data/publications.json`)
- `presentations.astro` — talks and slides

### 4. Publications — `src/data/publications.json`

```json
{
  "id": 1,
  "title": "Paper Title",
  "authors": "You, Coauthor A",
  "journal": "Journal or Conference Name",
  "year": 2025,
  "link": "https://...",
  "authorship": "first",
  "abstract": "...",
  "doi": "10.xxxx/xxxxx",
  "publicationType": "Journal"
}
```

`authorship`: `"first"`, `"last"`, or `"other"`. Drives the authorship filter.
`publicationType`: any string — `"Journal"`, `"Conference"`, `"Preprint"`, `"Book Chapter"`, etc. Each unique value becomes a filter button.

See `src/data/README.md` for full field details.

### 5. Blog posts — `src/pages/blog/`

Add a `.md` file per post:

```markdown
---
layout: '../../layouts/BlogPost.astro'
title: 'Post Title'
date: '2025-06-01'
description: 'One sentence shown on the index.'
tags: ['methodology', 'field-notes']
---

Post content here.
```

Tags become clickable filters on the blog index. Keep them lowercase and hyphenated, and reuse them across posts so the filter is useful.

Images go in `public/images/blog/` and are referenced as `/images/blog/filename.png`.

### 6. Adding or removing pages

Any `.astro` file in `src/pages/` becomes a route. To add a page, copy an existing one and add a link in `src/components/Navigation.astro`. To remove one, delete the file and remove its nav link.

### 7. Colours and fonts

Accent colour and font are set in `src/styles/global.css`. The font is loaded from Google Fonts — swap the import and the `font-family` declaration to change it.

## Deployment

### GitHub Pages

Push to `main` and GitHub Actions deploys automatically (workflow at `.github/workflows/deploy.yaml`).

**Recommended:** rename the repo to `your-github-username.github.io`. GitHub will serve it at `https://your-github-username.github.io` with no further configuration needed.

If you keep a different repo name (such asa `astro-scholar`), the site will be at `https://your-github-username.github.io/repo-name` and you'll need to set `base` in `astro.config.mjs`:

```javascript
export default defineConfig({
  site: 'https://your-github-username.github.io',
  base: '/repo-name',
});
```

### Other hosts

[Netlify](https://netlify.com), [Vercel](https://vercel.com), and [Cloudflare Pages](https://pages.cloudflare.com) all support Astro with minimal configuration. Or build with `npm run build` and upload `dist/` anywhere.

## Project structure

```
src/
├── constants.ts              # Name, tagline, social links
├── assets/portrait.png       # Profile picture
├── data/publications.json    # Publications
├── pages/
│   ├── index.astro
│   ├── about.astro
│   ├── publications.astro
│   ├── presentations.astro
│   └── blog/
│       ├── index.astro
│       └── *.md
├── layouts/
│   ├── Layout.astro
│   └── BlogPost.astro
├── components/
└── styles/
public/
├── presentations/            # HTML slide decks
├── posters/
└── images/blog/              # Blog post images
```

## License

MIT — see [LICENSE](LICENSE).

Created by [whydevils](https://github.com/whydevils). If you use this template, a star on GitHub is appreciated ⭐
