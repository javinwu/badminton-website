# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.
You are able to use the Svelte MCP server, where you have access to comprehensive Svelte 5 and SvelteKit documentation. Here's how to use the available tools effectively:

## Available MCP Tools:

### 1. list-sections

Use this FIRST to discover all available documentation sections. Returns a structured list with titles, use_cases, and paths.
When asked about Svelte or SvelteKit topics, ALWAYS use this tool at the start of the chat to find relevant sections.

### 2. get-documentation

Retrieves full documentation content for specific sections. Accepts single or multiple sections.
After calling the list-sections tool, you MUST analyze the returned documentation sections (especially the use_cases field) and then use the get-documentation tool to fetch ALL documentation sections that are relevant for the user's task.

### 3. svelte-autofixer

Analyzes Svelte code and returns issues and suggestions.
You MUST use this tool whenever writing Svelte code before sending it to the user. Keep calling it until no issues or suggestions are returned.

### 4. playground-link

Generates a Svelte Playground link with the provided code.
After completing the code, ask the user if they want a playground link. Only call this tool after user confirmation and NEVER if code was written to files in their project.

## Project Overview

This is a SvelteKit application for the San Ramon Valley High School Badminton team/club website. Built with SvelteKit 2, Svelte 5, TypeScript, and Tailwind CSS v4. Deployed to Vercel.

## Package Manager

**IMPORTANT**: This project uses **pnpm** as the package manager. Always use `pnpm` commands, never `npm` or `yarn`.

## Common Commands

### Development

```bash
pnpm dev              # Start development server
pnpm dev -- --open    # Start dev server and open in browser
```

### Building & Preview

```bash
pnpm build    # Build production version
pnpm preview  # Preview production build locally
```

### Code Quality

```bash
pnpm check           # Run svelte-check with TypeScript checking
pnpm check:watch     # Run svelte-check in watch mode
pnpm lint            # Run prettier check and eslint
pnpm format          # Format all files with prettier
```

## Architecture

### Framework & Routing

- **SvelteKit 2** with **Svelte 5** (using new runes syntax like `$props()`)
- File-based routing in `src/routes/`
- Root layout at `src/routes/+layout.svelte` imports global CSS and handles favicon
- Main page at `src/routes/+page.svelte`

### Styling

- **Tailwind CSS v4** via `@tailwindcss/vite` plugin
- Global styles in `src/routes/layout.css`
- Component-scoped `<style>` blocks for custom animations (sparkle, shine, bounce-slam)
- Color scheme: Dark green (#006400), Gold (#FFD700), light green backgrounds

### Deployment

- Uses `@sveltejs/adapter-vercel` for Vercel deployment
- Pre-configured in `svelte.config.js`

### TypeScript Configuration

- Strict mode enabled
- Extends `.svelte-kit/tsconfig.json`
- `rewriteRelativeImportExtensions: true` for modern import handling
- Path aliases handled by SvelteKit (`$lib` automatically configured)

### Code Style

- **Prettier**: Tabs, single quotes, no trailing commas, 100 char line width
- Tailwind plugin integration for class sorting
- **ESLint**: TypeScript + Svelte plugins with flat config format
- `no-undef` disabled (TypeScript handles this)

## Key Technical Details

### SvelteKit Conventions

- `+page.svelte` = route pages
- `+layout.svelte` = layout wrappers
- `+page.ts/js` or `+layout.ts/js` = load functions (none currently used)
- `src/lib/` = aliased as `$lib` for imports

### Svelte 5 Runes

This project uses Svelte 5's new runes syntax:

- `$props()` instead of `export let`
- `{@render children()}` for slot content

### Current Pages

- Home page (`/`) - Main landing page with hero, CTAs, team/club forms
- Gallery page link exists in nav but route not yet implemented

### Static Assets

- Favicon in `src/lib/assets/favicon.svg`
- External images hosted on CDNs (postimg.cc, unsplash, etc.)
- Static files go in `static/` directory

## Development Notes

- The `pnpm-workspace.yaml` exists with `onlyBuiltDependencies: [esbuild]` for workspace optimization
- No server-side routes or API endpoints currently
- No database or backend services
- Purely static/client-side application
