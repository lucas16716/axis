# AXIS — Favicon Assets

This directory stores favicon and application icon files used by browsers and mobile devices.

Favicons help identify the website in browser tabs, bookmarks, and when users add the site to their home screen.

## Essential Files

The following files are recommended for modern web compatibility:

- `favicon.svg` → scalable icon for modern browsers
- `apple-touch-icon.png` → 180×180 icon used when adding the site to the iOS home screen
- `favicon.ico` → optional fallback for legacy browsers

## Example Usage

Typical favicon setup inside the `<head>`:

```html
<link rel="icon" type="image/svg+xml" href="/assets/favicon/favicon.svg" />
<link rel="apple-touch-icon" href="/assets/favicon/apple-touch-icon.png" />
```

## Guidelines

Favicons should be:

- simple and recognizable at small sizes
- exported with proper padding
- optimized for clarity at 16px–32px

When designing favicons, avoid excessive details or thin shapes that may become unreadable at small resolutions.

## Naming Convention

Use consistent lowercase naming.

Examples:

- `favicon.svg`
- `apple-touch-icon.png`
- `favicon.ico`