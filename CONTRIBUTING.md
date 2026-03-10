# Contributing to AXIS

Thank you for taking the time to contribute. AXIS is an open project and all contributions are welcome — whether it's a bug report, a suggestion, a fix, or a new component.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Bug Reports](#bug-reports)
- [Suggesting Improvements](#suggesting-improvements)
- [Pull Requests](#pull-requests)
- [New Components & Tokens](#new-components--tokens)
- [Commit Style](#commit-style)

## Code of Conduct

Be respectful. Constructive feedback is always welcome; hostility is not. Contributions that disrespect other contributors or maintainers will not be accepted.

## Bug Reports

Found something broken or behaving unexpectedly? Open an issue and include:

- A clear description of the problem
- Steps to reproduce it
- What you expected to happen vs. what actually happened
- Browser and OS if relevant

Keep the issue focused on a single problem. If you found multiple bugs, open separate issues.

## Suggesting Improvements

Have an idea that could make AXIS better? Open an issue with the `enhancement` label and describe:

- What you'd like to see added or changed
- Why it fits the AXIS philosophy (simple, token-driven, dependency-free)
- Any references or examples that illustrate the idea

Not every suggestion will be accepted — AXIS is intentionally minimal. If a feature would add complexity without clear architectural benefit, it's likely out of scope. But the conversation is always welcome.

## Pull Requests

Before opening a PR, please open an issue first so we can discuss the change. This avoids wasted effort if the direction isn't aligned.

When submitting a PR:

1. Fork the repository and create a branch from `main`
2. Name your branch descriptively — e.g. `fix/button-disabled-state` or `feat/new-mixin`
3. Keep the change focused — one PR per fix or feature
4. Follow the existing code style (see below)
5. Test your changes across modern browsers before submitting
6. Write a clear PR description explaining what changed and why

## New Components & Tokens

AXIS ships with a deliberately small set of components and tokens. New additions are evaluated against the following criteria:

**For components:**
- Must be neutral — no hardcoded colors, no visual opinions
- Must use `currentColor` or inherit from context
- Must follow the existing BEM-light naming convention (`.component`, `.component__element`, `.is-modifier`)
- Must not require JavaScript to function

**For tokens:**
- Must be genuinely reusable across different project types
- Primitive tokens belong in `abstracts/tokens/`
- Semantic tokens belong in the partial where they are consumed
- Avoid adding tokens that duplicate existing ones with marginal differences

If you're unsure whether something fits, open an issue and ask before building it.

## Commit Style

Follow [Conventional Commits](https://www.conventionalcommits.org):

```
feat: add grid-auto responsive modifier
fix: correct button disabled opacity token
docs: update mixin usage examples
refactor: simplify respond() mixin logic
chore: clean up trailing whitespace
```

Keep commit messages short and in the present tense. One logical change per commit.

## Acknowledgements

Every contribution helps AXIS evolve and become a better foundation for frontend projects.
Thank you for being part of it.

## Support the Project

If AXIS has been useful to you, consider supporting its development:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)