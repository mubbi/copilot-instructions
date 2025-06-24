# GitHub Copilot Custom Instructions for Next.js v15 with App Router, TypeScript & Jest

These instructions guide Copilot to generate modern, clean, scalable, and production-ready Next.js 15 code using the App Router, TypeScript, and Jest for testing. Code must align with industry best practices for React, TypeScript, accessibility, performance, and maintainability.

---

## ✅ General Project Standards

- Always use **TypeScript**, avoid untyped JavaScript files.
- Follow **ESLint**, **Prettier**, and **TypeScript strict mode** configurations.
- Prefer functional components with **arrow functions**.
- Follow the **separation of concerns** principle: components, hooks, utilities, and services are organized in their respective folders.
- Use descriptive, meaningful, and consistent file, component, and variable names.
- Avoid inline styles or excessive logic inside components.

---

## ✅ Next.js v15 & App Router Best Practices

- Use the **App Router** exclusively (`app/` directory structure).
- Pages should be defined using `page.tsx` files inside route folders.
- Use **Server Components** by default unless client-side interactivity is needed.
- Mark interactive components explicitly with `"use client"` at the top.
- Leverage **Route Groups**, **Parallel Routes**, and **Layouts** for structured routing.
- Use `generateStaticParams` and `generateMetadata` for dynamic routes and SEO.
- Use **loading.tsx** and **error.tsx** files for route-level loading and error handling.
- Use **Next.js `Image`** component for optimized images.
- Use **next/font** for font management, avoid custom `<link>` tags.
- Avoid usage of deprecated Pages Router patterns (e.g., `pages/` directory).

---

## ✅ TypeScript Best Practices

- Enable strict mode (`"strict": true` in `tsconfig.json`).
- All components and functions must have explicit **typed props** and return types.
- Use `interface` or `type` consistently for defining props and complex types.
- Prefer **utility types** (`Partial`, `Pick`, `Record`, etc.) where suitable.
- Avoid `any` unless absolutely necessary; use unknown with type guards if needed.
- Leverage **discriminated unions**, **enums**, and **literal types** where appropriate.
- Write reusable types for shared data structures.

---

## ✅ Component Development

- Use **functional, stateless components** by default.
- Keep components **small**, **focused**, and with a **single responsibility**.
- For complex state, use `useState` or `useReducer`.
- Share logic via **custom hooks** inside `hooks/` directory.
- Avoid deeply nested components; extract reusable UI elements.
- Follow proper accessibility (a11y) standards:
  - Use semantic HTML.
  - Add appropriate `aria-*` attributes.
  - Ensure interactive elements (buttons, links) are properly labeled.

---

## ✅ Styling Best Practices

- Use **CSS Modules** or **Tailwind CSS** for styling.
- Avoid global styles unless necessary (prefer `globals.css` for true global styles).
- For design systems, integrate with **shadcn/ui**, **Radix UI**, or equivalent if applicable.
- Maintain consistent theming and responsive design.
- Avoid inline styles unless dynamic or conditionally applied.

---

## ✅ State & Data Management

- For server-side data:
  - Use `fetch()` or libraries like `next-safe-fetch` inside **Server Components**.
  - Handle caching with `revalidate` options or `cache: 'no-store'` as needed.
- For client-side state:
  - Use `useState`, `useReducer`, or context sparingly.
  - For global state, prefer `Zustand`, `Jotai`, or **React Context** if justified.
- Avoid unnecessary global state; co-locate state where possible.

---

## ✅ API Routes & Backend Integration

- For API routes:
  - Use `app/api` structure with route-specific files.
  - Validate all incoming requests, preferably with **zod** or equivalent.
  - Return typed responses.
- For external API calls:
  - Use a dedicated `services/` or `lib/api/` layer.
  - Handle errors gracefully.
  - Avoid directly calling APIs inside components unless trivial.

---

## ✅ Testing with Jest & React Testing Library

- Use **Jest** with **React Testing Library** for component and logic testing.
- Tests must:
  - Reside in `__tests__/` directories or alongside components as `*.test.tsx`.
  - Be isolated, repeatable, and avoid shared state.
  - Include meaningful assertions.
  - Cover rendering, user interaction, and state changes.
- Mock external dependencies (APIs, router, etc.) where applicable.
- Prefer **integration tests** for critical flows.
- Consider adding **Playwright** or **Cypress** for E2E tests (optional).

---

## ✅ Code Quality & Maintainability

- Follow **SOLID** and **KISS** principles:
  - Small, reusable, composable components.
  - Minimal logic in components; extract to hooks or services.
- Avoid code duplication.
- Document complex logic with comments or `README.md` in relevant folders.
- Apply type-safe error handling.
- Use **absolute imports** via `tsconfig.paths` or `next.config.js` for cleaner imports.

---

## ✅ Performance & Optimization

- Use **dynamic imports** with `suspense` or `loading` fallbacks for large components.
- Leverage image and font optimizations provided by Next.js.
- Minimize bundle size:
  - Avoid unnecessary third-party libraries.
  - Tree-shake unused code.
- Use `revalidate` strategies or caching for optimal API performance.
- Follow **Lighthouse** and **Core Web Vitals** recommendations.

---

## ✅ Additional Copilot Behavior Preferences

- Suggest **strictly typed**, modern TypeScript code.
- Default to Next.js 15 **App Router** patterns only.
- Prefer **Server Components** where possible.
- Avoid Pages Router, legacy patterns, and untyped code.
- Recommend tests alongside new components or logic.
- Suggest accessibility improvements (ARIA, semantic elements).
- Favor clean, readable, production-ready code over clever or shortcut solutions.
