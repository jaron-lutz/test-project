# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Vue 3 + TypeScript + Vite application with shadcn-vue component library integration, Tailwind CSS for styling, and Pinia for state management.

## Essential Commands

**Package Management:**
- Use `npx pnpm install` to install dependencies (pnpm not installed globally)
- Use `npx pnpm` prefix for all pnpm commands

**Development:**
- `npx pnpm dev` - Start development server (runs on http://localhost:5173/)
- `npx pnpm build` - Type-check with vue-tsc and build for production
- `npx pnpm preview` - Preview production build locally

**shadcn-vue Components:**
- `npx shadcn-vue@latest add <component>` - Add shadcn-vue components
- Configuration is in `components.json` (New York style, TypeScript enabled)
- Components are added to `src/components/ui/`

## Architecture

**Application Entry:**
- `src/main.ts` - Application entry point that initializes Vue app, Pinia store, and Vue Router
- `src/App.vue` - Root component

**State Management:**
- Pinia stores use Composition API style (setup stores)
- Located in `src/stores/`
- Example: `useCounterStore` in `src/stores/counter.ts` demonstrates the pattern

**Routing:**
- Vue Router configured in `src/router/index.ts`
- Uses `createWebHistory` mode
- Routes defined as typed `RouteRecordRaw[]` array
- Views are in `src/views/`, routed components in `src/components/`

**Path Aliases:**
- `@/*` resolves to `src/*` (configured in both `vite.config.ts` and `tsconfig.json`)
- shadcn-vue specific aliases: `@/components`, `@/lib/utils`, `@/components/ui`, `@/lib`, `@/hooks`

**Styling:**
- Tailwind CSS configured with `neutral` base color and CSS variables enabled
- Main styles in `src/style.css`
- `cn()` utility in `src/lib/utils.ts` for conditional class merging (clsx + tailwind-merge)

**TypeScript Configuration:**
- Project uses TypeScript project references
- `tsconfig.json` - Base config with path aliases
- `tsconfig.app.json` - App-specific compiler options
- `tsconfig.node.json` - Node/Vite config compilation

**MCP Integration:**
- shadcn-vue MCP server configured in `.mcp.json`
- Provides component search, installation, and examples through Claude Code's MCP tools
