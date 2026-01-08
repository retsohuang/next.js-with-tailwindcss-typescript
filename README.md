# Next.js Monorepo with Shared UI Library

A monorepo setup with a shared UI library using Style Dictionary v5 for design tokens and a Next.js app with Tailwind CSS v4.

## Current Versions

- Next.js 16 (with Turbopack)
- React 19
- Tailwind CSS 4
- TypeScript 5
- Turborepo 2
- Style Dictionary 4

## Project Structure

```
├── apps/
│   └── web/                 # Next.js 16 app with Tailwind CSS v4
├── packages/
│   └── ui/                  # Shared UI library with Style Dictionary
├── turbo.json               # Turborepo configuration
└── pnpm-workspace.yaml      # PNPM workspace configuration
```

## Try it Online

[![Open in CodeSandbox](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/p/github/retsohuang/next.js-with-tailwindcss-typescript/claude/monorepo-ui-library-setup-1RADC)

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/retsohuang/next.js-with-tailwindcss-typescript/tree/claude/monorepo-ui-library-setup-1RADC)

## Development Setup

You will need [Node.js](https://nodejs.org) **version 18+**, and [PNPM](https://pnpm.io).

After cloning the repo, run:

```bash
# Install dependencies
pnpm install

# Build the UI library (generates design tokens)
pnpm run build --filter @repo/ui

# Start development server with Turbopack
pnpm run dev
```

## Available Scripts

| Command | Description |
|---------|-------------|
| `pnpm run dev` | Start development server with Turbopack |
| `pnpm run build` | Build all packages with Turborepo |
| `pnpm run lint` | Lint all packages |
| `pnpm run clean` | Clean all build artifacts |

## Design Tokens

Design tokens are defined in `packages/ui/src/tokens/colors.json` using the DTCG format. Style Dictionary generates CSS custom properties that are consumed by Tailwind CSS.

Available color scales:
- `primary` (50-950)
- `secondary` (50-950)
- `neutral` (50-950)
- `success` (50, 500, 700)
- `warning` (50, 500, 700)
- `error` (50, 500, 700)

Usage in Tailwind:
```html
<div class="text-primary-600 bg-secondary-100">
  Styled with design tokens
</div>
```
