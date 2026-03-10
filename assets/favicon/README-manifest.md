# AXIS — Web App Manifest

The `manifest.json` file tells the browser how to install your website as a **Progressive Web App (PWA)** — enabling features like "Add to Home Screen" on mobile, a custom splash screen, and standalone display without the browser UI.

This file is **optional**. Your site works normally without it. Include it only if your project intends to support PWA installation.

---

## Fields

**`name`**
Full application name. Displayed on the splash screen and app store listings.

**`short_name`**
Shortened name displayed under the home screen icon when space is limited (max ~12 characters recommended).

**`description`**
Brief description of the application purpose.

**`start_url`**
The URL loaded when the app is launched from the home screen. Use `"/"` for the root, or a specific path if needed.

**`display`**
Controls how the app appears when launched:

- `standalone` → runs like a native app, no browser UI
- `browser` → opens in the regular browser
- `fullscreen` → hides all system UI (games, media apps)
- `minimal-ui` → browser UI with minimal controls

**`background_color`**
Background color shown on the splash screen while the app loads. Should match your page background to avoid a flash of color.

**`theme_color`**
Color applied to the browser/OS chrome (status bar, tab bar). Should match your `<meta name="theme-color">` in `index.html`.

**`icons`**
Array of icon sizes used across devices:

- `192x192` → Android home screen, splash screen
- `512x512` → higher-res splash screen and app stores
- `purpose: "maskable"` → allows the OS to apply its own icon shape (rounded corners, circle, etc.)

---

## Required Icons

Add the following files to this directory:

```
favicon/
├── icon-192.png       → 192×192px
├── icon-512.png       → 512×512px
├── apple-touch-icon.png → 180×180px (already referenced in index.html)
└── favicon.svg        → scalable (already referenced in index.html)
```

Use a tool like [RealFaviconGenerator](https://realfavicongenerator.net) or [Maskable.app](https://maskable.app) to generate and test your icons.

---

## Reference

- [MDN — Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest)
- [web.dev — Add a Web App Manifest](https://web.dev/add-manifest/)
