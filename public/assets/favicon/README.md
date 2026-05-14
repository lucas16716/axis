# AXIS — Favicon Assets

This directory stores modern favicon and application icon files used by browsers and mobile devices.

> **Note:** The legacy fallback `favicon.ico` is stored directly in the project's root directory (alongside `index.html`). This is a best practice, as legacy browsers and bots automatically request `/favicon.ico` by default.

## Essential Files in this folder

The following files are recommended for modern web compatibility:

- `favicon.svg` → Scalable icon, prioritized by all modern browsers.
- `favicon.png` → Standard PNG fallback.
- `apple-touch-icon.png` → 180×180 icon used when users add the site to their iOS home screen.

## Example Usage

Typical favicon setup inside the `<head>` of your `index.html`:

```html
<link rel="icon" type="image/svg+xml" href="/assets/favicon/favicon.svg" />
<link rel="icon" type="image/png" href="/assets/favicon/favicon.png" />
<link rel="apple-touch-icon" href="/assets/favicon/apple-touch-icon.png" />
```
