# PerceptMind

Marketing landing page built with Astro and GSAP.

## Tech stack

- Astro 5
- TypeScript (strict Astro config)
- GSAP animations
- Custom design tokens (`src/styles/colors.css`, `src/styles/sizes.css`)

## Local development

```sh
npm install
npm run dev
```

## Quality checks

```sh
npm run check
npm run lint
npm run test
```

## Build and preview

```sh
npm run build
npm run preview
```

## Project structure

- `src/layouts/Layout.astro` - global HTML shell and SEO meta tags
- `src/pages/index.astro` - hero section and page-level animation logic
- `src/components/NeuralBackground.astro` - animated SVG neural background
- `src/components/Navbar.astro` - fixed top navigation
- `src/components/Contact.astro` - contact CTA section
- `src/styles/global.css` - global styles and font-face declarations
- `src/styles/colors.css` - color tokens
- `src/styles/sizes.css` - typography and spacing tokens

## Performance and accessibility notes

- Respects `prefers-reduced-motion` in both hero and background animations.
- Background animation uses bounded propagation depth and packet concurrency.
- Keyboard focus styles are enabled for interactive links.
- Font loading uses `woff2` (+ `otf` fallback), `font-display: swap`, and preloaded critical weights.
