# AXIS — Video Assets

This directory stores video files used across the project, including background videos, short animations, and other motion media.

## Recommended Formats

Prefer modern, web-optimized formats:

- `.webm` → primary format (smaller file size and better compression)
- `.mp4` → fallback for broader browser compatibility

Example usage:

```html
<video autoplay muted loop playsinline>
  <source src="/assets/media/video/hero-loop.webm" type="video/webm" />
  <source src="/assets/media/video/hero-loop.mp4" type="video/mp4" />
</video>
```

## Performance Guidelines

Video files can significantly impact page performance.

Always:

- Compress videos before adding them to the project
- Keep resolution appropriate for the layout
- Avoid unnecessarily long clips
- Prefer short looping background videos

Recommended tools:

- HandBrake
- FFmpeg
- Online video compressors (ILovePDF or Adobe Acrobat)

## GIF vs Video

Avoid using `.gif` when possible.

GIF files are usually:

- heavier
- lower quality
- inefficient for animation

Instead, use short `.mp4` or `.webm` videos with:

- `autoplay`
- `muted`
- `loop`
- `playsinline`

This approach provides better performance and visual quality.

## Naming Convention

Use consistent lowercase naming with hyphens.

Examples:

- `hero-background-loop.mp4`
- `product-demo.webm`
- `intro-animation.mp4`

Avoid:

- spaces
- uppercase letters
- special characters