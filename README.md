# Ryze

**Ryze** is a modern, minimalist theme / template built with **Astro v5**, **Tailwind CSS v4**, and optimized for static sites, responsiveness, and SEO. Perfect for personal blogs and content-focused websites.

Read the [blog posts](https://ryze.pages.dev/) to understand how Ryze is built and how to customize it for your own site.

## ✅ Features

- [x] Modern & minimalist design with responsive layout
- [x] Light & Dark mode with system preference detection
- [x] Static site generation for optimal performance
- [x] Automatic sitemap and RSS feed generation
- [x] SEO optimization (Open Graph, Twitter Cards, Canonical URLs)
- [x] Markdown-based blog posts with frontmatter metadata
- [x] Syntax highlighting with Shiki
- [x] Featured posts and tag-based organization
- [x] Archive and chronological browsing
- [x] Reading time estimation
- [x] TypeScript support
- [x] Component-based architecture with Astro & React
- [x] Tailwind CSS v4 for styling
- [x] Code quality tools (ESLint & Prettier)

## Lighhouse Performance Scores

<p align="center">
  <a href="https://pagespeed.web.dev/report?url=https%3A%2F%2Fryze.pages.dev%2F&form_factor=desktop">
    <img width="710" alt="Ryze Lighthouse score" src="ryze-lighthouse-score.svg">
  <a>
</p>

## Project Structure

```
/
├── public/
│   └── favicon.svg
│
├── src/
│   ├── blog/
│   │   ├── post-title.md
│   │   ├── another-post.md
│   │   └── ... (add your posts here)
│   │
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── Navigation.astro
│   │   ├── Seo.astro
│   │   ├── Title.astro
│   │   ├── PostCard.astro
│   │   ├── Featured.astro
│   │   ├── PostNavigation.astro
│   │   ├── Pagination.astro
│   │   ├── ThemeToggle.tsx
│   │   ├── ProgressBar.tsx
│   │   ├── Index.tsx
│   │   ├── Introduction.astro
│   │   ├── Newsletter.astro
│   │   ├── Socials.astro
│   │   ├── FeatureCard.astro
│   │   └── Year.astro
│   │
│   ├── layouts/
│   │   ├── BaseLayout.astro
│   │   └── BlogLayout.astro
│   │
│   ├── pages/
│   │   ├── index.astro
│   │   ├── [...slug].astro
│   │   ├── 404.astro
│   │   ├── rss.xml.ts
│   │   ├── robots.txt.ts
│   │   ├── archive/
│   │   │   ├── [page].astro
│   │   │   └── [year]/[page].astro
│   │   └── tags/
│   │       ├── index.astro
│   │       └── [tag]/[page].astro
│   │
│   ├── styles/
│   │   ├── global.css
│   │   └── typography.css
│   │
│   ├── image/
│   │
│   └── content.config.ts
│
├── astro.config.mjs
├── tailwind.config.js
├── tsconfig.json
├── eslint.config.js
├── package.json
└── README.md
```

## Tech Stack

- [Astro v5](https://astro.build) - Static site generator
- [React](https://reactjs.org/) - UI library for interactive components
- [TypeScript](https://www.typescriptlang.org/) - Typed JavaScript superset
- [Tailwind CSS v4](https://tailwindcss.com/) - Utility-first CSS framework
- [Tabler Icons](https://tabler-icons.io/) - Icon library
- [Fontsource](https://fontsource.org/) - Self-hosted web fonts
- [Cloudflare Pages](https://www.cloudflare.com/products/pages/) - Deployment platform
- [Shiki](https://shiki.matsu.io/) - Syntax highlighting
- [RSS](https://www.npmjs.com/package/rss) - RSS feed generation
- [Sitemap](https://www.npmjs.com/package/sitemap) - Sitemap generation
- [ESLint](https://eslint.org/) & [Prettier](https://prettier.io/) - Code quality and formatting

## Installation

```bash
# Clone or download the project
cd ryze

# Install dependencies
npm install

# Start development server
npm run dev
```

The site will be available at `http://localhost:4321`

### Commands

| Command             | Description                        |
| ------------------- | ---------------------------------- |
| `npm run dev`       | Start local development server     |
| `npm run build`     | Build production-ready static site |
| `npm run preview`   | Preview production build locally   |
| `npm run astro ...` | Run Astro CLI commands             |

## Feedback & Suggestions

Have feedback or ideas? Reach out via [email](mailto:deploy.rahul@gmail.com) or [open an issue](https://github.com/yourusername/ryze/issues) to report bugs or suggest new features.

## 📜 License

See [LICENSE](LICENSE) for more information.
