# AXIS — Assets Directory

This directory contains all **static media and downloadable resources** used across the project.

Assets are organized by media type to keep the project structure clear, scalable, and easy to maintain.

## Directory Structure

```
assets/
├── docs/
├── favicon/
├── media/
│   ├── img/
│   └── video/
└── svg/
```

## Directory Overview

**docs/**  
Downloadable documents such as PDFs, manuals, forms, or other files intended for user download.

**favicon/**  
Browser icons and device icons used for tabs, bookmarks, and mobile home screens.

**media/**
- **img/** → raster images (`.webp`, `.jpg`, `.png`)
- **video/** → video assets (`.webm`, `.mp4`) for backgrounds or animations

**svg/**
Vector graphics such as icons, logos, and scalable illustrations.

## General Guidelines

- Always optimize media before adding it to the project.
- Prefer modern, web-optimized formats.
- Use consistent lowercase naming with hyphens.
- Avoid spaces, uppercase letters, and special characters in filenames.

Example:

- `hero-background.webp`
- `product-demo.webm`
- `company-logo.svg`
- `product-manual.pdf`

A well-organized assets structure helps maintain **performance, consistency, and scalability** across the project.