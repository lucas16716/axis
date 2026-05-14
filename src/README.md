# AXIS — Source Files

This directory contains the development source code for the AXIS project.

With the adoption of Vite, this folder represents the raw, uncompiled state of the application. Everything here is processed, optimized, and bundled into the `dist/` folder for production.

**Structure:**

- `js/` The core of the application. Contains the main entry point (`script.js`) and the modular JavaScript architecture (`base/`, `components/`, `vendor/`). It also acts as the bundler master, importing the Sass architecture directly.

- `sass/` 5-layer Sass architecture following ITCSS principles. Contains design tokens, global styles, components, and layouts. These files are imported into the JavaScript entry point and processed in-memory by Vite, eliminating the need for physical CSS files during development.
