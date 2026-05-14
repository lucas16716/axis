# Contributing to AXIS

Thank you for taking the time to contribute. AXIS is an open project and all contributions are welcome — whether it's a bug report, a suggestion, a fix, or a new component.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Bug Reports](#bug-reports)
- [Development Setup](#development-setup)
- [New Components & Modules](#new-components--modules)
- [Suggesting Improvements](#suggesting-improvements)
- [Pull Requests](#pull-requests)
- [Commit Style](#commit-style)

## Code of Conduct

Be respectful. Constructive feedback is always welcome; hostility is not. Contributions that disrespect other contributors or maintainers will not be accepted.

## Bug Reports

Found something broken or behaving unexpectedly? Open an issue and include:

- A clear description of the problem.
- Steps to reproduce it.
- Browser and OS if relevant.

## Development Setup

AXIS uses **Vite** to manage the development environment. To start contributing:

1. Fork and clone the repository.
2. Install dependencies: `npm install`
3. Start the dev server: `npm run dev`
4. Open the local URL in your browser — changes are reflected instantly via HMR.

## New Components & Modules

AXIS ships with a deliberately small set of components. New additions are evaluated against these criteria:

**For CSS Components:**

- Must be neutral — no hardcoded project-specific colors.
- Must follow the BEM-light naming convention (`.component`, `.component__element`, `.is-modifier`).

**For JS Modules:**

- Must be written as **ES Modules**.
- Place logic in `src/js/components/` or `src/js/base/`.
- Must be imported and initialized via the main entry point (`src/js/script.js`).

**For Tokens:**

- Must be reusable across different project types.
- Primitive tokens belong in `abstracts/tokens/`.

## Suggesting Improvements

Have an idea to make AXIS better? Open an issue with the `enhancement` label and describe:

- What you'd like to see added or changed.
- Why it fits the AXIS philosophy (**minimalist, token-driven, and lightweight**).

AXIS is intentionally minimal. If a feature adds too much complexity without clear benefit, it might be considered out of scope.

## Pull Requests

Before opening a PR, please open an issue first so we can discuss the change. When submitting:

1. Create a branch from `main`.
2. Name your branch descriptively — e.g., `fix/button-alignment` or `feat/modal-module`.
3. Keep the change focused — one PR per fix or feature.
4. Run `npm run build` before submitting to ensure there are no bundling errors.
5. Write a clear PR description explaining what changed and why.

## Commit Style

Follow [Conventional Commits](https://www.conventionalcommits.org):

```
feat: add accordion component logic
fix: resolve z-index conflict in header
docs: update installation steps in README
refactor: migrate utility classes to new token system
```

Keep commit messages short and in the present tense. One logical change per commit.

## Acknowledgements

Every contribution helps AXIS evolve and become a better foundation for frontend projects. Thank you for being part of it.

## Support the Project

If AXIS has been useful to you, consider supporting its development:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)
