# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
pnpm install       # Install dependencies
pnpm dev           # Start dev server (opens browser at localhost:3030)
pnpm run build     # Build for production → ./dist (base path: /slidev-sst)
pnpm run export    # Export presentation to PDF/images
```

There are no tests in this project.

## Architecture

This is a [Slidev](https://sli.dev) presentation project — a Vue 3-based framework for creating Markdown-driven slide decks.

### Content structure

- **`slides.md`** — Entry point. Declares frontmatter (theme, highlighter, transitions) and imports page modules via `src:` directives.
- **`pages/`** — Modular slide sections imported by `slides.md`. Each file is an independent set of slides concatenated into the final deck.
- **`components/`** — Vue 3 components available globally in any slide without importing.
- **`snippets/`** — TypeScript/code files with `// #region` markers that can be embedded in slides via `<<< @/snippets/file.ts#region-name`.

### Frontmatter (slides.md)

```yaml
theme: default
highlighter: shiki
transition: fade
css: unocss
mdc: true  # enables Markdown Components (::component-name:: syntax)
```

### Deployment

Built output goes to `./dist`. The repo's GitHub Pages deployment copies `dist/` to `../docs/` at the repository root. `netlify.toml` and `vercel.json` are also configured for alternative hosting.

The `--base /slidev-sst` flag in the build command must match the GitHub Pages subpath.
