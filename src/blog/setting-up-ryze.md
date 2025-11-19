---
slug: "setting-up-ryze"
title: "Setting Up Ryze — Step-by-step"
description: "Step-by-step setup for Ryze with exact commands, common failures and fixes, and where to look next."
date: 2025-11-20
author: "Rahul"
tags: ["ryze", "setup", "astro", "tutorial"]
featured: true
---

This guide walks through cloning, installing dependencies, running the dev server, and resolving the most common setup failures. It is direct — follow the commands and checks exactly.

Prerequisites (exact)

- Node.js 18.x or later (LTS recommended). Why: Astro v5 requires modern Node features and stable async handling.
- One of: `npm` (bundled with Node), `yarn`, or `pnpm`. Examples below use `npm`.

1. Clone the repository

Use HTTPS unless you have SSH keys configured.

```powershell
git clone https://github.com/yourusername/ryze.git
cd ryze
```

If you prefer SSH:

```powershell
git clone git@github.com:yourusername/ryze.git
cd ryze
```

2. Install dependencies

Use `npm ci` on CI or `npm install` locally. If you already have `node_modules` or an old lockfile, remove them first.

```powershell
# Fresh install
npm install

# CI (reproducible)
npm ci
```

If you run into permission errors on Windows, do not use `sudo`. Ensure your Node installation is correctly installed for your user account or use `nvm-windows` to manage versions.

3. Run the development server

```powershell
npm run dev
```

Open `http://localhost:4321`. The dev server supports Hot Module Replacement; changes to `.astro`, `.md`, and `.css` files reload automatically.

Quick verification commands

- Node version: `node --version`
- npm version: `npm --version`
- Clean install: delete `node_modules` and `package-lock.json` then `npm ci`

Common installation problems and exact fixes

- "Unsupported Node version" — message: `Ryze requires Node 18.x or higher`. Fix: install Node 18 LTS and re-run `npm install`. On Windows, use `nvm-windows`.
- `EACCES` or permission errors — do not `sudo` on Windows. Fix: reinstall Node for current user or use `nvm-windows`. For macOS/Linux, configure an npm global prefix rather than using `sudo`.
- Lockfile mismatch or corrupted `node_modules` — delete `node_modules` and `package-lock.json` then `npm ci`.

Where to look when you want to customize next

- Edit `tailwind.config.js` to add brand colors or to add content globs if you add new extensions.
- Edit `src/styles/global.css` to add `@layer components` classes for repeated UI pieces (buttons, cards).
- Edit `src/layouts/BaseLayout.astro` to change global head tags and layout container widths.

Windows-specific tips

- Use PowerShell commands shown above. If you hit file-locking issues, close editors that may hold file handles (some editors keep watchers open).
- If dev server fails with `EADDRINUSE` (port in use), run `Get-Process -Id (Get-NetTCPConnection -LocalPort 4321).OwningProcess` in PowerShell to find the process and stop it, or edit your `package.json` dev script to change the port.

If you want, I can:

- Add a `README.windows.md` with PowerShell-specific notes.
- Add a `postinstall` script to `package.json` that validates Node version and prints fix instructions.

Next steps after setup

1. Run `npm run dev` and open `http://localhost:4321`.

- **pnpm** (fast, space-efficient package manager)

If you want, tell me which of the three next actions above to do and I’ll implement it (create sample post, update tailwind theme, or add postinstall checks).
This guide uses **npm**, but yarn and pnpm work equally well. All examples can be translated by replacing `npm` with your preferred manager:

```bash
# Using npm
npm install

# Using yarn
yarn install

# Using pnpm
pnpm install
```

### [Cloning the Repository](#cloning-the-repository)

Now that prerequisites are met, you need to get the Ryze repository on your computer. Choose the method that works best for you.

#### [HTTPS Method](#https-method)

The simplest method, no SSH keys required. Paste this command in your terminal:

```bash
git clone https://github.com/yourusername/ryze.git
cd ryze
```

If prompted for authentication, enter your GitHub username and a personal access token (instead of your password). You can generate one at [GitHub Settings → Developer Settings → Personal Access Tokens](https://github.com/settings/tokens).

<br />

**Advantages:**

- No setup required
- Works from anywhere
- Great for first-time users

**Disadvantages:**

- Requires personal access token or password
- Slower than SSH for repeated operations

#### [SSH Method](#ssh-method)

Faster and more secure if you've set up SSH keys with GitHub. If you haven't, follow [GitHub's SSH setup guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

```bash
git clone git@github.com:yourusername/ryze.git
cd ryze
```

**Advantages:**

- No credentials needed after setup
- Fastest method
- Industry standard for developers

**Disadvantages:**

- Requires initial SSH key setup
- Slightly higher learning curve

#### [GitHub CLI Method](#github-cli-method)

If you have [GitHub CLI](https://cli.github.com) installed, this is the quickest option:

```bash
gh repo clone yourusername/ryze
cd ryze
```

**Advantages:**

slug: "setting-up-ryze"
title: "Setting Up Ryze — Essentials"
description: "Essential steps to clone, install, and run Ryze locally."
date: 2025-11-20
author: "Rahul"
tags: ["ryze", "setup", "astro", "tutorial"]
featured: true

---

Essentials

- Node.js 18.x+ (LTS recommended)
- npm, yarn or pnpm (examples use `npm`)

Clone, install, run

```powershell
git clone https://github.com/yourusername/ryze.git
cd ryze
npm install
npm run dev
```

Preview: `http://localhost:4321`

Quick checks

- Verify Node: `node --version`
- If install fails, try `npm ci` or clear `node_modules` and `package-lock.json` then reinstall.

Project map (what you'll edit)

- `src/styles/global.css` — Tailwind directives and component layers
- `tailwind.config.js` — content globs and theme extensions
- `src/layouts/BaseLayout.astro` — global head and structure
- `src/components/*` — Header, Footer, PostCard, Seo
- `src/blog/*` — Markdown posts

Troubleshooting

- Mismatched Node: use nvm/nvm-windows to switch Node versions.
- Permission errors: prefer configuring npm prefix over `sudo`.

If you want, I can tighten `package.json` scripts or add Windows-friendly instructions.

By default in this project the dev server runs at `http://localhost:4321` (see `README.md`). Open that URL to preview your changes.

Dev features:

- Hot Module Replacement (HMR) for fast iteration
- Automatic rebuilds on file change

To stop the dev server: press `Ctrl + C` in the terminal.

## Project layout (high level)

Key folders you'll edit:

- `src/components/` — reusable UI pieces (Header.astro, Footer.astro, PostCard.astro, Seo.astro)
- `src/layouts/` — `BaseLayout.astro` and `BlogLayout.astro` wrap pages
- `src/pages/` — routes and dynamic pages (index.astro, blog/[slug].astro)
- `src/blog/` — your Markdown posts
- `src/styles/` — `global.css` and `typography.css` (Tailwind directives live here)

Edit these files to customize layout, theme, and content structure.

## What to edit first

1. Update `package.json` scripts or `astro.config.mjs` only if you know what you're changing.
2. Customize `tailwind.config.js` to set your brand colors and fonts.
3. Edit `src/layouts/BaseLayout.astro` for global HTML/head changes.
4. Author blog posts in `src/blog/` using frontmatter (see other guide post).

If you'd like, I can make a small PR to tweak colors or add a README section describing every component in `src/components/`.
theme: {
extend: {
colors: {
"brand-primary": "#FF6B6B",
"brand-secondary": "#4ECDC4",
},
},
}

````

Then use them in your HTML:

```html
<button class="bg-brand-primary hover:bg-brand-secondary">Click Me</button>
````

<br />

### [tsconfig / jsconfig](#tsconfig--jsconfig)

TypeScript configuration file: `tsconfig.json`

Ryze can use either TypeScript or JavaScript (or both). The config file tells Astro which language rules to follow.

```json
{
  "extends": "astro/configs/strict",
  "compilerOptions": {
    "moduleResolution": "bundler",
    "baseUrl": ".",
    "paths": {
      "@components/*": ["src/components/*"],
      "@layouts/*": ["src/layouts/*"],
      "@pages/*": ["src/pages/*"]
    }
  }
}
```

**Key options:**

- **moduleResolution**: How imports are resolved
- **baseUrl**: Base directory for imports
- **paths**: Aliases for cleaner imports

The aliases let you write:

```typescript
import Header from "@components/Header.astro";
// Instead of:
import Header from "../../../components/Header.astro";
```

Much cleaner!

<br />

## [Understanding Astro + Tailwind Integration](#understanding-astro--tailwind-integration)

### [Tailwind Injection](#tailwind-injection)

Tailwind doesn't just appear in your project. Astro integrates Tailwind through a specific process.

#### [PostCSS](#postcss)

PostCSS is a tool that processes CSS. Astro automatically configures PostCSS to:

1. Read Tailwind directives from `global.css`
2. Generate Tailwind's utility classes
3. Inject them into your pages

You don't need to do anything—Astro handles this automatically when you install `@astrojs/tailwind`.

<br />

#### [Directives](#directives)

Tailwind directives are special CSS commands that tell PostCSS what to include:

```css
/* In src/styles/global.css */

@import "tailwindcss"; /* Base styles (resets, defaults) */
@layer base {
  /* Add custom components */
  .btn-primary {
    @apply rounded-lg bg-blue-600 px-4 py-2 text-white hover:bg-blue-700;
  }
}
```

- **@tailwind base**: Resets and default styles
- **@tailwind components**: Pre-built component styles
- **@tailwind utilities**: All utility classes (most of Tailwind)
- **@layer components**: Add custom utility-like classes

<br />

### [Where Styles Live](#where-styles-live)

#### [global.css](#global-css)

Located at `src/styles/global.css`, this file runs on every page:

```css
@import "tailwindcss";
:root {
  --color-text: #1f2937;
  --color-background: #ffffff;
}

html.dark {
  --color-text: #f3f4f6;
  --color-background: #111827;
}

body {
  @apply bg-white text-gray-900 dark:bg-gray-900 dark:text-gray-100;
}
```

Use this for:

- CSS custom properties (variables)
- Dark mode definitions
- Global font settings
- General page styling

<br />

#### [Component Styles](#component-styles)

Styles can also live directly in components:

```astro
---
// src/components/Button.astro
---

<button class="rounded-lg bg-blue-600 px-4 py-2 text-white hover:bg-blue-700">
  <slot />
</button>

<style>
  button {
    transition: all 0.3s ease;
  }
</style>
```

Component styles are **scoped** to that component only—they don't affect other parts of your site. This is perfect for component-specific styling.

<br />

## [Build Process Explained](#build-process-explained)

Understanding how Astro builds your site helps you troubleshoot issues and optimize performance.

### [Astro Compiles Pages](#astro-compiles-pages)

When you run `npm run build`, Astro processes your entire project:

#### [Markdown to HTML](#markdown-to-html)

Markdown files in `src/blog/` are converted to HTML:

```markdown
---
title: "My Post"
---

# Hello World

This is a post.
```

Becomes:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Post</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a post.</p>
  </body>
</html>
```

The frontmatter metadata becomes available to your layout template, which wraps the HTML with headers, footers, and styling.

<br />

#### [Components to Static HTML](#components-to-static-html)

Astro components (`.astro` files) are also compiled to static HTML:

```astro
---
// src/components/PostCard.astro
interface Props {
  title: string;
  excerpt: string;
}

const { title, excerpt } = Astro.props;
---

<article class="rounded border p-4">
  <h2>{title}</h2>
  <p>{excerpt}</p>
</article>
```

Astro renders this to plain HTML at build time. **No JavaScript is sent to the browser** unless you explicitly add interactive components.

This is different from React, where component code is sent to the browser as JavaScript. Astro ships zero JavaScript by default.

<br />

### [Tailwind Tree-Shaking](#tailwind-tree-shaking)

Tailwind includes thousands of utility classes. Your site probably uses only a fraction of them. Tree-shaking removes unused styles.

#### [Removing Unused Styles](#removing-unused-styles)

Tailwind scans your files for class names:

```css
/* Before tree-shaking: ~45 KB */
.text-red-50 { ... }
.text-red-100 { ... }
.text-red-200 { ... }
/* ... hundreds more ... */

/* After tree-shaking: ~5 KB (only used classes) */
.px-4 { padding-left: 1rem; padding-right: 1rem; }
.bg-blue-600 { background-color: #2563eb; }
.hover\:bg-blue-700:hover { background-color: #1d4ed8; }
```

The `tailwind.config.js` file tells Tailwind which files to scan:

```javascript
content: ["./src/**/*.{astro,html,js,jsx,md,mdx,svelte,ts,tsx,vue}"],
```

This scans all files in `src` with these extensions. Only classes appearing in scanned files are included in the final CSS.

**Result**: Your final CSS file is tiny (usually 5-15 KB after gzipping), making your site incredibly fast.

<br />

### [Production Output](#production-output)

When you run `npm run build`, Astro creates a production-ready site.

#### [dist directory](#dist-directory)

The `dist/` folder contains your entire compiled website:

```
dist/
  ├── index.html            # Home page
  ├── 404.html              # Error page
  ├── robots.txt            # Search engine rules
  ├── sitemap-0.xml         # Sitemap
  ├── rss.xml               # RSS feed
  ├── blog/
  │   ├── post-1/index.html
  │   ├── post-2/index.html
  │   └── ...
  ├── tags/
  │   ├── astro/index.html
  │   ├── tailwind/index.html
  │   └── ...
  ├── archive/
  │   ├── 1/index.html
  │   ├── 2025/index.html
  │   └── ...
  ├── _astro/               # Compiled assets
  │   ├── styles.HASH.css
  │   ├── component.HASH.js
  │   └── ...
  └── public/               # Static assets
      ├── favicon.ico
      ├── images/
      └── ...
```

Every file is static HTML. No server needed. Just upload to any host (Netlify, Vercel, GitHub Pages, S3, etc.).

**Hashing in filenames**: Assets like `styles.HASH.css` include a hash. When you update styles, the hash changes, busting the browser cache. Old versions aren't cached, ensuring visitors get the latest version.

<br />

#### [Static assets](#static-assets)

Images and files from `public/` are copied directly to `dist/public/`:

- **No processing**: Images aren't optimized or transformed
- **Direct copies**: JPEG, PNG, SVG, PDF, etc. stay unchanged
- **Path same**: `/public/image.png` becomes `/image.png` in the site

For optimized images (auto-resizing, format conversion), use Astro's Image component with the `@astrojs/image` integration.

<br />

## [Next Steps](#next-steps)

Now that your project is set up and running, you're ready to start building:

1. **Customize styling**: Edit `tailwind.config.js` and `src/styles/` to match your brand
2. **Create pages**: Add `.astro` files to `src/pages/`
3. **Build components**: Create reusable Astro components in `src/components/`
4. **Write content**: Add markdown files to `src/blog/` with your posts
5. **Deploy**: Build with `npm run build` and deploy `dist/` folder

For deployment guides, check out [Astro's Deployment Documentation](https://docs.astro.build/en/guides/deploy/).

<br />

---

Happy building with Ryze! If you encounter issues, check the [Astro documentation](https://docs.astro.build) or reach out to the community. You've got this! 🚀

<figure class="group">
<img src="/src/image/background.svg" loading="lazy" alt="Ryze project setup workflow" title="From zero to running development server" />
<figcaption>Setting up Ryze gets you from zero to a running development server in minutes</figcaption>
</figure>
