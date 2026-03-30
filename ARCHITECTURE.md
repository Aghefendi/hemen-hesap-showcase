# HemenHesap Architecture: Modular Monolith (FSD)

This project follows the **Feature-Sliced Design (FSD)** architectural pattern, organized as a **Modular Monolith**. This ensures that as we add hundreds of calculation tools, the codebase remains maintainable, testable, and free of circular dependencies.

## 🏗️ Layered Structure

The project is divided into four main layers, each with a strict hierarchy:

### 1. `src/app` (The Routing Layer)
- Contains Next.js App Router pages, layouts, and global configurations.
- Minimal logic: mostly just assembling features into pages.

### 2. `src/features` (The Business Logic Layer)
- This is where 90% of the value resides.
- Organized by domain: `blog`, `calculators`, `taxi`, `admin`, etc.
- Each feature is a **vertical slice** containing its own components, hooks, types, and logic.

### 3. `src/core` (The Domain & Infrastructure Layer)
- **Domain:** Core business rules and models that never change.
- **Infrastructure:** Adapters for external services (GitHub API, Supabase, Upstash).

### 4. `src/shared` (The Foundation Layer)
- Reusable UI components (buttons, inputs, logos).
- Common utility functions and global types.
- Strict rule: **Shared cannot depend on any other layer.**

## 🚀 Key Patterns

### Discovery Pattern
The project uses a custom build-time discovery engine (`scripts/generate-calculators.ts`). It scans the `features/calculators` directory and automatically generates:
- Sitemaps
- Arama İndeksi (Search Index)
- Navigation links
- Dynamic routes

### Zero Circular Dependencies
We enforce a strict one-way dependency flow. Features can depend on `core` and `shared`, but never on each other. This is monitored via `madge`.

### Programmatic SEO
By combining **Next.js ISR** with our modular data layer, we serve thousands of SEO-optimized pages with zero manual work per page.
