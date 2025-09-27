# Chatbot Widget - AI Coding Instructions

## Project Overview

This is a **chatbot widget** built with React + TypeScript + Vite, designed as an embeddable component. The project uses **shadcn/ui** components with **Tailwind CSS v4** and the **New York** style variant.

## Architecture & Key Technologies

### Build System

- **Vite** with SWC for fast React development (`pnpm dev`)
- **TypeScript** with strict configuration across `tsconfig.app.json` and `tsconfig.node.json`
- Build command: `pnpm build` (runs TypeScript check then Vite build)

### Styling System

- **Tailwind CSS v4** with `@tailwindcss/vite` plugin integration
- **shadcn/ui** components configured in `components.json` with "new-york" style
- Custom CSS variables in `src/index.css` following shadcn theme system
- **tw-animate-css** for animations
- Use `cn()` utility from `src/lib/utils.ts` for conditional class merging

### Component Patterns

- Components should be added via `pnpm dlx shadcn@latest add <component-name>`
- Follow shadcn/ui conventions: components in `@/components/ui`, utilities in `@/lib`
- Path aliases configured: `@/` maps to `./src/`
- CSS variables follow the pattern `--color-*` and `--radius-*` for theming

## Development Workflow

### Commands

```bash
pnpm dev          # Start development server
pnpm build        # TypeScript check + production build
pnpm lint         # ESLint with React hooks and refresh rules
pnpm preview      # Preview production build
```

### Adding Components

1. Use shadcn CLI: `pnpm dlx shadcn@latest add button card dialog`
2. Components auto-install to `src/components/ui/`
3. Import using path alias: `import { Button } from "@/components/ui/button"`

## Project-Specific Conventions

### File Organization

```
src/
├── components/ui/     # shadcn/ui components (auto-generated)
├── lib/utils.ts       # Utility functions (cn helper, etc.)
├── App.tsx           # Main widget component (currently empty)
└── index.css         # Tailwind + theme variables
```

### Widget Architecture

Since this is a **chatbot widget**, consider:

- The main widget should be self-contained and embeddable
- State management for chat messages and UI state
- Event handling for user interactions
- Responsive design for various container sizes

### Styling Guidelines

- Use `cn()` for conditional classes: `cn("base-classes", condition && "conditional-classes")`
- Leverage CSS variables for theming: `var(--primary)`, `var(--radius)`
- Dark mode support via `dark:` variants and `.dark` class
- Follow shadcn component patterns for consistency

## Dependencies to Know

- **class-variance-authority**: For component variant patterns
- **lucide-react**: Icon library (configured in shadcn)
- **tailwind-merge + clsx**: Class name merging (via `cn()` utility)
- **React 19**: Latest React features available

## Common Tasks

- **Adding new components**: Always use shadcn CLI first, then customize
- **Styling**: Use Tailwind classes with `cn()` for conditional logic
- **Icons**: Import from `lucide-react`: `import { MessageCircle } from "lucide-react"`
- **Theme customization**: Modify CSS variables in `src/index.css`
