# Changelog

All notable changes to AXIS will be documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] — 2026/03/10

Initial release.

### Added

**Architecture**
- Five-layer Sass architecture following ITCSS principles: Abstracts → Base → Layout → Components → Sections
- Single entry point `main.scss` with full `@use` / `@forward` module system — no `@import`
- `.vscode/settings.json` pre-configured for Live Sass Compiler with dual output: expanded (`src/css/`) and compressed (`dist/`)

**Design Tokens** — 9 token files in `abstracts/tokens/`
- `_colors.scss` — grayscale scale (white → black) + 4 functional colors (green, yellow, red, blue)
- `_spacing.scss` — 8pt macro grid, micro UI scale, and semantic tokens `$gutter` and `$section-pad`
- `_typography.scss` — Major Third (1.25) scale + UI sizes, weights, line-heights and letter-spacings
- `_breakpoints.scss` — 6 desktop-first breakpoints: xxl, xl, lg, md, sm, xs
- `_motion.scss` — 5 durations + 4 easing curves (standard, in, out, back)
- `_elevation.scss` — 5 shadow levels (none → lg)
- `_layers.scss` — semantic z-index map: back, base, header, dropdown, overlay, modal, tooltip
- `_radius.scss` — 6 radius values: xs, sm, md, lg, xl, full
- `_opacity.scss` — 6 levels: 0, 20, 40, 60, 80, 100

**Functions** — `abstracts/functions/`
- `bp()` — safe breakpoint map access with `@error` on invalid keys
- `z()` — semantic z-index access with `@error` on invalid keys
- `color-dark()` / `color-light()` — color scaling via `color.scale()`

**Mixins** — `abstracts/mixins/`
- `container()` — centered wrapper with `padding-inline` and `margin-inline`
- `flex()` — shorthand flex container with optional direction, justify, align and gap
- `grid()` — fixed-column grid with configurable gap
- `grid-auto()` — responsive auto-fit grid using `minmax(min(100%, $min), 1fr)`
- `respond()` — desktop-first `max-width` media query
- `respond-up()` — `min-width` media query for progressive enhancement
- `absolute-center` — position absolute + translate(-50%, -50%)
- `focus-ring()` — accessible outline with configurable color and offset
- `visually-hidden` — accessible SR-only pattern
- `truncate()` — single-line and multi-line text truncation via `-webkit-line-clamp`

**Base layer**
- `_reset.scss` — box-sizing, margin/padding reset, accessible `focus-visible`, `text-size-adjust`, `scroll-behavior`
- `_typography.scss` — system-ui font stack, Major Third heading scale (h1 3.815rem → h6 1.25rem)
- `_global.scss` — responsive media, font inheritance for form elements, `prefers-reduced-motion`
- `_utilities.scss` — `.sr-only`, display, responsive visibility (`.hide-{bp}-down` / `.hide-{bp}-up`), position, text alignment, `.truncate`, `.truncate-2`, `.no-select`

**Layout layer**
- `_container.scss` — `.container` (default 1200px) + `.container-{sm|md|lg|xl|xxl}`
- `_flex.scss` — `.flex` with `flex-col`, `flex-wrap`, `justify-{start|center|between|end}`, `items-{stretch|center|start|end}`
- `_grid.scss` — `.grid-{1-12}`, `.col-span-{1-12}`, `.grid-auto`, responsive variants `.grid-{n}-{bp}` and `.col-span-{n}-{bp}`

**Components**
- `_button.scss` — base `.button`, sizes (sm/md/lg/xl), shapes (square/circle), variants (pill/ghost), disabled state
- `_card.scss` — `.card`, `.is-interactive` with hover/focus/active transitions, `.card__content` with `is-start`, `is-center`, `is-end`
- `_badge.scss` — inline pill badge using `currentColor`

**Sections**
- `_header.scss` and `_footer.scss` — empty partials, ready for project-specific styles

**Project structure**
- `index.html` — full meta setup: charset, viewport, SEO, Open Graph, Twitter Card, PWA manifest, favicons
- `assets/favicon/manifest.json` — PWA manifest template with icons
- `dist/script.min.js` — placeholder for manually minified JavaScript
- READMEs in every directory with guidelines, tips and best practices

---

### Upcoming Versions

Possible future improvements include:
- new base components
- documentation improvements
- example projects built with AXIS

---

*For upcoming changes, see open [issues](https://github.com/lucas16716/axis/issues) and [pull requests](https://github.com/lucas16716/axis/pulls).*