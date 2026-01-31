# Personal Website - Volker Seeker

A modern, single-page personal website built with [Astro](https://astro.build) and [Tailwind CSS](https://tailwindcss.com).

## Features

- Clean, professional academic design
- Responsive mobile-first layout
- Dark mode with system preference detection
- Smooth scrolling navigation
- Publication cards with award badges
- Timeline-style career bio

## Project Structure

```
astro-site/
├── public/
│   ├── images/           # Profile image
│   ├── favicon/          # Favicon files
│   ├── files/papers/     # PDF papers
│   └── CNAME             # Custom domain
├── src/
│   ├── components/       # Astro components
│   │   ├── Icons/        # SVG icon components
│   │   ├── Hero.astro
│   │   ├── About.astro
│   │   ├── Bio.astro
│   │   ├── Publications.astro
│   │   └── ...
│   ├── data/             # JSON data files
│   │   ├── publications.json
│   │   ├── bio.json
│   │   ├── research-interests.json
│   │   └── social-links.json
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │   └── index.astro
│   └── styles/
│       └── global.css
├── astro.config.mjs
└── package.json
```

## Getting Started

### Prerequisites

- Node.js 18+ (install via `brew install node` on macOS)
- npm (comes with Node.js)

### Development

```bash
# Install dependencies
npm install

# Start the development server
npm run dev

# Open http://localhost:4321 in your browser
```

### Building for Production

```bash
# Build the site
npm run build

# Preview the production build locally
npm run preview
```

## Updating Content

### Publications

Edit `src/data/publications.json` to add, update, or remove publications:

```json
{
  "id": "unique_id",
  "title": "Paper Title",
  "authors": ["Author 1", "Author 2", "V. Seeker"],
  "venue": "CGO",
  "venueFullName": "IEEE/ACM International Symposium on Code Generation and Optimization",
  "year": 2024,
  "award": "Best Paper Award",  // Optional - remove if no award
  "links": {
    "pdf": "/files/papers/paper.pdf",       // Local PDF
    "preprint": "/files/papers/preprint.pdf",
    "arxiv": "https://arxiv.org/abs/...",
    "ieee": "https://ieeexplore.ieee.org/...",
    "acm": "https://dl.acm.org/...",
    "slides": "/files/talks/slides.pdf"
  }
}
```

To add a new paper PDF, place it in `public/files/papers/` and reference it with `/files/papers/filename.pdf`.

### Bio/Career Timeline

Edit `src/data/bio.json`:

```json
{
  "dateRange": "Since Apr. '24",
  "role": "Research Engineer",
  "organization": "Meta AI Research",
  "location": "Menlo Park, California, USA",
  "current": true  // Optional - adds highlight ring
}
```

### Research Interests

Edit `src/data/research-interests.json` (simple string array):

```json
[
  "Large Language Models for code optimization",
  "Autotuning of compilers",
  "..."
]
```

### Social Links

Edit `src/data/social-links.json`:

```json
{
  "platform": "github",  // github, linkedin, scholar, orcid
  "url": "https://github.com/vsee",
  "label": "GitHub"
}
```

### Profile Image

Replace `public/images/profile.png` with a new image (recommended: square, at least 400x400px).

## Deployment

### GitHub Pages (Automatic)

The site automatically deploys to GitHub Pages when you push to the `main` branch.

1. Go to your repository Settings > Pages
2. Under "Build and deployment", select "GitHub Actions" as the source
3. Push your changes to `main`
4. The site will be available at your custom domain (configured in `public/CNAME`)

### Manual Deployment

```bash
npm run build
# Upload contents of ./dist to your hosting provider
```

## Customization

### Colors

Edit the color theme in `src/styles/global.css`:

```css
@theme {
  --color-primary-500: #3b82f6;  /* Main accent color */
  /* ... other shades */
}
```

### Typography

The site uses Inter for body text. To change fonts, update the Google Fonts link in `src/layouts/Layout.astro` and the font-family in `src/styles/global.css`.

### Adding a Projects Section

Uncomment the Projects section placeholder in `src/pages/index.astro`:

```astro
{/* Future Projects Section
<Section id="projects" title="Projects">
  <p>Coming soon...</p>
</Section>
*/}
```

## Commands Reference

| Command           | Action                                      |
| :---------------- | :------------------------------------------ |
| `npm install`     | Install dependencies                        |
| `npm run dev`     | Start dev server at `localhost:4321`        |
| `npm run build`   | Build production site to `./dist/`          |
| `npm run preview` | Preview production build locally            |

## Tech Stack

- [Astro](https://astro.build) - Static site generator
- [Tailwind CSS](https://tailwindcss.com) - Utility-first CSS framework
- [TypeScript](https://www.typescriptlang.org) - Type safety

## License

MIT
