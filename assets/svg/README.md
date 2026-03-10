# AXIS — SVG Assets

This directory stores vector graphics used across the project, including icons, logos, illustrations, and interface graphics.

SVG files are resolution-independent and ideal for modern web interfaces.

## Usage Guidelines

SVGs can be used in different ways depending on the use case:

**1. Inline SVG (recommended for icons and UI elements)**
Allows styling with CSS and better control over color and states.

```html
<svg class="icon">
  <use href="/assets/svg/icons.svg#arrow"></use>
</svg>
```

**2. Image source**

```html
<img src="/assets/svg/logo.svg" alt="Company logo" />
```

**3. CSS background**

```css
.logo {
  background-image: url("/assets/svg/logo.svg");
}
```

## Best Practices

Always keep SVG files clean and optimized.

- Remove unnecessary metadata exported from design tools
- Simplify paths when possible
- Avoid inline styles inside SVG files
- Prefer `currentColor` for icons that should inherit text color

Example:

```svg
<path fill="currentColor" d="..."/>
```

This allows color control directly from CSS.

## Optimization

Before adding SVG files to the project, run them through an optimizer.

Recommended tools:

- SVGO
- SVGOMG
- Built-in export optimization from Figma or Illustrator

Optimized SVGs reduce file size and improve performance.

## Naming Convention

Use consistent lowercase naming with hyphens.

Examples:

- `logo-primary.svg`
- `icon-arrow.svg`
- `illustration-dashboard.svg`

Avoid:

- spaces
- uppercase letters
- special characters