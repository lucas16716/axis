# AXIS — Image Assets

This directory stores raster image files used across the project, including photos, backgrounds, UI graphics, and other bitmap-based media.

Raster images are resolution-dependent and should always be optimized for web performance.

## Recommended Formats

Prefer modern, optimized formats whenever possible:

- `.webp` → primary format (best compression and performance)
- `.jpg` → good for photographs and complex images
- `.png` → use only when transparency is required

Example usage:

```html
<img src="/assets/media/img/hero-banner.webp" alt="Hero banner image" />
```

## Performance Guidelines

Images are one of the most common causes of slow websites.

Always:

- Compress images before adding them to the project
- Resize images to the maximum size actually needed
- Avoid uploading original high-resolution files directly
- Prefer responsive images when appropriate

Example using responsive images:

```html
<img
  src="/assets/media/img/hero-banner.webp"
  srcset="
    /assets/media/img/hero-banner-768.webp   768w,
    /assets/media/img/hero-banner-1200.webp 1200w
  "
  sizes="(max-width: 768px) 100vw, 1200px"
  alt="Hero banner image"
/>
```

## Optimization Tools

Before adding images to the project, run them through an optimizer.

Recommended tools:

- Squoosh
- TinyPNG / TinyJPG
- Photoshop or Figma export optimization

Optimized images improve loading speed and overall site performance.

## Naming Convention

Use consistent lowercase naming with hyphens.

Examples:

- `hero-banner.webp`
- `product-photo.jpg`
- `team-member-avatar.png`

Avoid:

- spaces
- uppercase letters
- special characters