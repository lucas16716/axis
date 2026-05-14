# AXIS — JavaScript Architecture

This directory contains the modular JavaScript architecture and the main entry point used by AXIS.

**Structure:**

- `base/` Global scripts, helpers, and utility functions (e.g., globals, formatters).

- `components/` Isolated JavaScript logic for UI components (e.g., menus, modals, tabs).

- `vendor/` Configuration and initialization for third-party libraries (e.g., Swiper, GSAP).

- `script.js` The main entry point. It acts as the bundler master, importing all JS modules and the Sass architecture to be processed by Vite.
