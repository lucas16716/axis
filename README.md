<div align="center">

<img src="public/assets/favicon/favicon.svg" width="130" height="130" alt="AXIS symbol"/>

# AXIS

**A modern Sass architecture and starter foundation for scalable, maintainable web projects**

_Structure your frontend. Focus on building, not configuring_

[![Version](https://img.shields.io/badge/version-2.0.0-e8e4de?style=flat-square&labelColor=10b981&color=1c1b2e)](https://github.com/lucas16716/axis/releases)&nbsp; [![Template](https://img.shields.io/badge/template-ready-e8e4de?style=flat-square&labelColor=3437e6&color=1c1b2e)](https://github.com/lucas16716/axis/generate)&nbsp; [![License](https://img.shields.io/badge/license-MIT-e8e4de?style=flat-square&labelColor=ef4444&color=1c1b2e)](https://github.com/lucas16716/axis/blob/main/LICENSE)&nbsp; ![GitHub Repo stars](https://img.shields.io/github/stars/lucas16716/axis?style=social)

🇧🇷 [Leia em Português](./README-ptbr.md)

</div>

## What is AXIS?

AXIS is a modern Sass-based architecture powered by Vite, designed to structure frontend projects in a clear, scalable, and maintainable way.

It combines the simplicity of traditional development (HTML, Sass and JavaScript) with the power of modern build tooling. Vite delivers an instant development server with HMR and an automated production pipeline that compiles, prefixes and minifies everything for you. Clone it, install dependencies, define your semantic tokens, and start building on a solid base: normalized reset, configured typography, a functional layout system, neutral components ready for your visual identity, and utilities that accelerate development — so the focus stays on what matters: building the interface.

## Philosophy

AXIS is built around six core principles:

**Modern and agile development** — Vite drives the entire development experience, eliminating complex configuration and focusing on speed. Node.js and NPM make the project scalable and enable professional integration of external libraries.

**Architectural simplicity** — The folder structure is direct and predictable. Each layer — both in Sass and in JavaScript — has a single, clear responsibility. JavaScript follows the ES Modules pattern, keeping logic organized in isolated, clean files.

**Modular Sass architecture** — Five clearly separated layers that communicate through `@use` and `@forward`, creating a logical style hierarchy: Abstracts → Base → Layout → Components → Sections. Everything is processed in-memory during development for maximum performance.

**Token-driven design** — All visual values come from tokens. Primitive tokens are centralized in `abstracts/tokens/` and globally accessible via `@use`. Semantic tokens are defined locally in the partial where they are consumed — eliminating unnecessary file navigation and keeping values close to where they are used.

> E.g.: semantic tokens in `base/_typography.scss` for typography, in `abstracts/tokens/_spacing.scss` for layout configuration, and inside each component partial for its own padding, transition and sizing values.

**Desktop-first workflow** — The architecture starts from the largest layout and adapts downward via `@include respond()`. Full support for `respond-up()` is included for progressive enhancement when needed.

**Automation and performance** — The entire compilation, prefixing and minification pipeline (CSS and JS) is automated by Vite. No third-party extensions or manual steps needed. `index.html` ships pre-configured with SEO and Open Graph meta tags, and an efficient favicon strategy (`.ico` at root for crawler compatibility, modern formats in `public/assets/favicon/`). Every folder and file in AXIS includes documentation, tips and comments guiding frontend best practices.

## Stack

| Technology  | Usage                                           |
| ----------- | ----------------------------------------------- |
| Vite        | Dev server (HMR) and automated production build |
| HTML5       | Base template with SEO, OG and PWA meta tags    |
| Sass (SCSS) | Modular architecture with design tokens         |
| JavaScript  | Modular architecture based on native ES Modules |

## Project Structure

```
axis/
├── public/
│   ├── assets/
│   │   ├── docs/                → Downloadable documents
│   │   ├── favicon/             → Modern icons (.svg, .png)
│   │   ├── media/
│   │   │   ├── img/             → Raster images (.webp, .jpg, .png)
│   │   │   └── video/           → Videos (.webm, .mp4)
│   │   └── svg/                 → Vectors, icons, and illustrations
│   ├── favicon.ico              → Legacy icon (root level for bot compatibility)
│   └── manifest.json            → PWA settings and browser icons
├── src/
│   ├── js/
│   │   ├── base/                → Global scripts and utility functions
│   │   ├── components/          → Isolated component logic (menu, modal)
│   │   ├── vendor/              → Third-party library configs (Swiper, GSAP)
│   │   └── script.js            → Master entry point — imports JS modules and Sass
│   └── sass/
│       ├── abstracts/           → Tokens, functions, and mixins
│       ├── base/                → Reset, typography, and global styles
│       ├── layout/              → Container, flex, and grid utilities
│       ├── components/          → Neutral UI component styles
│       ├── sections/            → Project-specific section styles
│       └── main.scss            → Sass entry point (imported via script.js)
├── .gitignore                   → Files ignored by Git (node_modules, dist)
├── CHANGELOG.md                 → Record of all notable project changes
├── CONTRIBUTING.md              → Guidelines for contributing to the project
├── index.html                   → Main project template
├── LICENSE                      → Project license (MIT)
├── package.json                 → NPM dependencies and automation scripts
├── README.md                    → English documentation
├── README-ptbr.md               → Portuguese documentation
└── vite.config.js               → Vite configuration (dev server, build, paths)
```

## Sass Architecture

AXIS organizes Sass into **five layers** with clear responsibilities, following ITCSS principles:

**1. Abstracts** — Nothing here generates CSS directly. This is the entire foundation of the system.

- **`tokens/`** — 9 design token files with generic, standardized and scalable values: colors, spacing, typography, breakpoints, motion, elevation, layers, radius and opacity
- **`functions/`** — typed token access via `bp()` and `z()`, and color helpers using `color.scale()`
- **`mixins/`** — container, flex, grid, grid-auto, respond, respond-up, absolute-center, focus-ring, visually-hidden and truncate

**2. Base** — Normalization and global styles without classes.

- **`_reset.scss`** — box-sizing, margin/padding reset, accessible focus-ring, text-size-adjust and scroll-behavior
- **`_typography.scss`** — base font with semantic tokens, Major Third (1.25) heading scale
- **`_global.scss`** — responsive media, font inheritance, prefers-reduced-motion
- **`_utilities.scss`** — sr-only, display, responsive visibility, position, text alignment, truncate and interaction

**3. Layout** — Structural layout system with no visual opinions.

- **`_container.scss`** — `.container` and variants `.container-{sm|md|lg|xl|xxl}`
- **`_flex.scss`** — `.flex` with direction, justify and align modifiers
- **`_grid.scss`** — `.grid-{1-12}`, `.col-span-{1-12}`, `.grid-auto` and responsive variants

**4. Components** — Neutral, token-driven components. No hardcoded colors — they use `currentColor` and inherit from context.

- **`_button.scss`** — sizes (sm/md/lg/xl), shapes (square/circle), variants (pill/ghost), disabled state
- **`_card.scss`** — static and interactive, with `card__content` structure and content alignment modifiers
- **`_badge.scss`** — inline, pill, neutral

**5. Sections** — Empty partials for **header** and **footer**, ready to be styled per project.

## Design Tokens

| File                | What it defines                                                                                     |
| ------------------- | --------------------------------------------------------------------------------------------------- |
| `_colors.scss`      | Grayscale (white → black) + 4 functional colors (green, yellow, red, blue)                          |
| `_spacing.scss`     | 8pt macro scale (layout) + micro scale (UI controls) + semantic tokens `$gutter` and `$section-pad` |
| `_typography.scss`  | 18 sizes (Major Third + UI), weights, line-heights and letter-spacings                              |
| `_breakpoints.scss` | 7 desktop-first breakpoints: xxl, xl, lg, md, sm, xs, xxs                                           |
| `_motion.scss`      | 5 durations + 4 easing curves (standard, in, out, back)                                             |
| `_elevation.scss`   | 5 shadow levels (none → lg)                                                                         |
| `_layers.scss`      | Semantic z-index: back, base, sticky, header, dropdown, overlay, modal, tooltip                     |
| `_radius.scss`      | 6 radius values: xs, sm, md, lg, xl, full                                                           |
| `_opacity.scss`     | 6 levels: 0, 20, 40, 60, 80, 100                                                                    |

## Layout System

### Container

```html
<div class="container">
  <!-- max-width: 1200px (default via mixin) -->
  <div class="container-sm"><!-- max-width: 640px --></div>
  <div class="container-md"><!-- max-width: 768px --></div>
  <div class="container-lg"><!-- max-width: 1024px --></div>
  <div class="container-xl"><!-- max-width: 1200px --></div>
  <div class="container-xxl"><!-- max-width: 1280px --></div>
</div>
```

### Flex

```html
<div class="flex items-center justify-between">
  <div class="flex flex-col items-start">
    <div class="flex flex-wrap justify-center"></div>
  </div>
</div>
```

Available modifiers: `flex-col`, `flex-wrap`, `justify-start`, `justify-center`, `justify-between`, `justify-end`, `items-stretch`, `items-center`, `items-start`, `items-end`.

### Grid

```html
<div class="grid-3">
  <!-- 3 fixed columns -->
</div>

<div class="grid-3 grid-1-md">
  <!-- 3 columns → 1 column at md -->
</div>

<div class="grid-auto">
  <!-- automatic responsive columns -->
  <div class="col-span-2"><!-- item spans 2 columns --></div>
</div>
```

> Responsive variants `.grid-{n}-{bp}` override only `grid-template-columns`. The base class `.grid-{n}` must always be present on the element.

## Components

### Button

```html
<!-- Sizes -->
<button class="button size-sm">Small</button>
<button class="button size-md">Medium</button>
<button class="button size-lg">Large</button>
<button class="button size-xl">X-Large</button>

<!-- Variants -->
<button class="button size-md is-pill">Pill</button>
<button class="button size-md is-ghost">Ghost</button>
<button class="button size-md" disabled>Disabled</button>

<!-- Shapes -->
<button class="button size-md shape-square">⊕</button>
<button class="button size-md shape-circle">→</button>
```

### Card

```html
<div class="card">
  <div class="card__content is-start">
    <h4>Title</h4>
    <p>Card content.</p>
  </div>
</div>

<!-- Interactive card -->
<div class="card is-interactive">
  <div class="card__content is-center">...</div>
</div>
```

Alignment modifiers: `is-start`, `is-center`, `is-end`.

### Badge

```html
<span class="badge">Default</span>
```

The badge inherits color via `currentColor` — apply color through the parent element, directly via `style`, or through a color class from your project.

## Mixins

Use mixins directly in your section or component partials:

```scss
@use "../abstracts/mixins" as mix;
@use "../abstracts/tokens" as token;

.my-component {
  @include mix.flex($justify: center, $align: center);
}

.my-overlay {
  @include mix.absolute-center;
}

.my-input:focus-visible {
  @include mix.focus-ring(token.$blue-500, 3px);
}

@include mix.respond(md) {
  // styles for md and below
}
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/lucas16716/axis.git your-project-name
cd your-project-name
```

### 2. Install dependencies

```bash
npm install
```

### 3. Start the development server

```bash
npm run dev
```

Vite starts a local dev server with HMR. Any change to `.scss` or `.js` files is reflected instantly in the browser — no manual compilation needed.

### 4. Start building

Add sections in `src/sass/sections/` and register them in `sections/_index.scss`. Define semantic tokens in the partials where they are consumed and use AXIS layout classes and components as the foundation.

### 5. Build for production

```bash
npm run build
```

Vite compiles, prefixes and minifies all CSS and JavaScript automatically. The optimized output is placed in the `dist/` folder, ready for deploy.

## Starting a New Project with AXIS

When cloning AXIS for a new project, the recommended workflow is:

1. **Update `index.html`** — replace SEO, OG and Twitter Card placeholders with real project data
2. **Define your visual identity** — update `public/manifest.json` with the project name, theme color and icons
3. **Configure your semantic tokens** — add semantic color variables to `_colors.scss` and adjust typography values in `_typography.scss` for the chosen typeface
4. **Style header and footer** — `sections/_header.scss` and `sections/_footer.scss` are empty and ready for the project
5. **Create your sections** — add new partials in `sections/` and register them in `sections/_index.scss`

## Production Optimization

Running `npm run build` triggers Vite's full production pipeline — CSS and JavaScript are automatically compiled, prefixed and minified. No manual steps required.

For projects where final bundle size is critical, consider using **PurgeCSS** to remove unused CSS classes from the production output.

→ [purgecss.com](https://purgecss.com)

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md) for details on how to open issues and propose changes.

If AXIS has been useful in your project, consider supporting its development:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)

## License

MIT License — © 2026 Lucas Couto

See the [LICENSE](./LICENSE) file for details.

## Author

Built with lots of code and coffee by [Lucas Couto](https://linkedin.com/in/lucas-coutoti).

See my work or get in touch at [Lucas Code](https://bio.site/lucascode).
