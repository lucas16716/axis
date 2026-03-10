# AXIS — Document Assets

This directory stores static documents that can be accessed or downloaded from the website.

Typical files include:

- `.pdf`
- `.doc` / `.docx`
- `.txt`
- spreadsheets
- other downloadable resources

These files are usually linked directly from the interface using standard HTML links.

## Example Usage

```html
<a href="/assets/docs/product-manual.pdf" download> Download Product Manual </a>
```

## Recommended Format

Whenever possible, convert documents to PDF before adding them to the project.

PDF files ensure:

- consistent layout across devices
- better compatibility with browsers
- easier access for users without requiring specific software

## Performance Guidelines

Large document files can negatively impact user experience.

Always:

- compress PDFs before uploading
- avoid unnecessarily large files
- keep documents optimized for web distribution

Recommended tools:

- ILovePDF
- Adobe Acrobat
- other PDF compression tools

## Naming Convention

Use consistent lowercase naming with hyphens.

Examples:

- `product-manual.pdf`
- `event-floor-plan.pdf`
- `terms-of-service.pdf`

Avoid:

- spaces
- uppercase letters
- special characters
- version numbers in filenames (`manual-v2-final.pdf`)