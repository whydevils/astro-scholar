# Astro Scholar

A modern, elegant academic website template built with [Astro](https://astro.build). Designed specifically for researchers, academics, and scholars to showcase their work, publications, and professional profile.

## ✨ Features

- **Clean, Professional Design** - Elegant serif typography (Spectral) perfect for academic content
- **Publications Management** - Dynamic filtering by year, type (journal/conference), and authorship
- **Responsive & Modern** - Mobile-first design that works beautifully on all devices
- **Dark Mode** - Built-in theme toggle for comfortable reading in any environment
- **Fast & Lightweight** - Built with Astro for optimal performance
- **Easy to Customize** - Well-organized code with clear documentation
- **Accessible** - Semantic HTML and ARIA labels for screen readers
- **SEO Ready** - Proper meta tags and structure for search engines

## 🚀 Quick Start

### Prerequisites

- Node.js 18 or higher
- npm (comes with Node.js)

### Installation

1. **Clone or download this repository**

```bash
git clone https://github.com/whydevils/astro-scholar.git
cd astro-scholar
```

2. **Install dependencies**

```bash
npm install
```

3. **Start the development server**

```bash
npm run dev
```

Your site will be running at `http://localhost:4321`

4. **Build for production**

```bash
npm run build
npm run preview  # Preview the production build locally
```

## 📝 Customization Guide

### 1. Site Configuration

Edit `src/constants.ts` to set your personal information:

```typescript
export const SITE_DATA = {
    name: "Your Name",
    tagline: "Your Title | Research Area | Institution",
    twitter: "your_twitter_handle",
    linkedin: "your-linkedin-username",
    scholar: "your_google_scholar_id",
    email: "your.email [at] example.com",
};
```

### 2. Profile Picture

Replace `src/assets/portrait.svg` with your own photo (`.jpg`, `.png`, or keep as `.svg`). Recommended size: 400x400px or larger, square format. Using assets enables Astro's automatic image optimization. Update the import in `src/components/Hero.astro` and `src/pages/about.astro` if changing the file extension.

### 3. Publications

Edit `src/data/publications.json`. Each publication should have:

```json
{
  "id": 1,
  "title": "Your Paper Title",
  "authors": "You, Coauthor A, Coauthor B",
  "journal": "Journal Name or Conference",
  "year": 2024,
  "link": "https://link-to-paper.com",
  "authorship": "first",  // "first", "last", or "other"
  "abstract": "Your paper abstract...",
  "doi": "10.xxxx/xxxxx",
  "publicationType": "Journal"  // "Journal", "Conference", "Preprint", or "Thesis"
}
```

See `src/data/README.md` for detailed field descriptions.

### 4. About Page

Edit `src/pages/about.astro`:

- Update the intro paragraph (lines 29-36)
- Replace work experience items with your positions
- Update education section with your degrees
- Modify the CV/contact sections as needed

### 5. Presentations

Edit `src/pages/presentations.astro` to add your talks and presentations. You can:

- Link to external slides (hosted elsewhere)
- Link to PDFs in `public/presentations/`
- Keep as plain text entries

### 6. Color Scheme

The accent color (currently Material Purple) can be changed in `src/styles/global.css`:

```css
:root {
    --color-accent: #6A1B9A;  /* Change this to your preferred color */
}

/* Also update dark mode: */
[data-theme="dark"] {
    --color-accent: #AB47BC;  /* Lighter shade for dark mode */
}
```

### 7. Font

To change the font, edit `src/styles/global.css`:

1. Update the Google Fonts import (line 6)
2. Update the font-family in the html selector (line 16)

## 📁 Project Structure

```
astro-scholar/
├── public/
│   ├── presentations/            # PDF files for presentations
│   └── posters/                  # PDF files for posters
├── src/
│   ├── assets/
│   │   ├── portrait.svg          # Your profile picture (replace with .jpg/.png)
│   │   └── icons/                # SVG icons
│   ├── components/
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   ├── Navigation.astro
│   │   ├── SocialIcons.astro
│   │   └── ThemeToggle.astro
│   ├── data/
│   │   ├── publications.json     # Your publications data
│   │   └── README.md             # Publications format guide
│   ├── layouts/
│   │   └── Layout.astro          # Main layout template
│   ├── pages/
│   │   ├── index.astro           # Homepage
│   │   ├── about.astro           # About/CV page
│   │   ├── publications.astro    # Publications list with filters
│   │   ├── presentations.astro   # Talks and presentations
│   │   └── 404.astro             # Error page
│   ├── scripts/
│   │   └── menu.js               # Mobile menu functionality
│   ├── styles/
│   │   ├── global.css            # Global styles and variables
│   │   ├── home.css              # Homepage-specific styles
│   │   ├── about.css             # About page styles
│   │   └── publications.css      # Publications page styles
│   └── constants.ts              # Site configuration
├── astro.config.mjs              # Astro configuration
├── package.json
└── tsconfig.json
```

## 🚢 Deployment

### GitHub Pages

1. Update `astro.config.mjs`:

```javascript
export default defineConfig({
  site: 'https://yourusername.github.io',
  base: '/your-repo-name',
});
```

2. The included GitHub Actions workflow (`.github/workflows/deploy.yaml`) will automatically deploy to GitHub Pages when you push to the main branch.

### Netlify

1. Connect your repository to Netlify
2. Build command: `npm run build`
3. Publish directory: `dist`
4. Deploy!

### Vercel

1. Import your repository to Vercel
2. Framework preset: Astro
3. Deploy!

### Other Hosts

Build the site with `npm run build` and upload the `dist/` folder to any static hosting service.

## 🛠️ Technologies Used

- **[Astro](https://astro.build)** - Web framework
- **[TypeScript](https://www.typescriptlang.org/)** - Type safety
- **[Spectral](https://fonts.google.com/specimen/Spectral)** - Typography (elegant serif font)
- **CSS3** - Styling with CSS variables for theming
- **Vanilla JavaScript** - Minimal, efficient interactivity

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🤝 Contributing

This is a template project. Feel free to fork and customize it for your needs! If you find bugs or have suggestions for improvements, please open an issue.

## 🙏 Credits

Created by [whydevils](https://github.com/whydevils)

---

**Happy publishing!** 🎓

If you use this template, consider giving it a star ⭐ on GitHub!
