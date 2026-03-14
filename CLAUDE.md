# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`astro-blocks` is an Astro component library. Components live in `src/components/` and are exported via `src/index.ts`. The library targets Astro as a peer dependency.

The `playground/` directory is a separate Astro app used to develop and preview the components locally. It has its own `package.json` and `node_modules`.

## Commands

From the repo root:

```sh
npm run playground        # Start the playground dev server (localhost:4321)
npm run playground:build  # Build the playground
```

From `playground/` directly:

```sh
npm run dev
npm run build
npm run preview
npm run astro -- --help
```

## Architecture

- **`src/components/`** — Astro component source files (`.astro`)
- **`src/index.ts`** — Public API; all components to be published must be exported here
- **`playground/`** — Standalone Astro app for manual testing; imports components directly from `src/` (not via npm)
- The root `package.json` has no build step — the library exports raw TypeScript/Astro source (`"exports": { ".": "./src/index.ts" }`)

## Adding Components

1. Create the component in `src/components/MyComponent.astro`
2. Export it from `src/index.ts`
3. Use it in `playground/src/pages/` to verify it visually
