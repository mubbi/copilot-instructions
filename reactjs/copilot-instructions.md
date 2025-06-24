# GitHub Copilot Custom Instructions for React 19 with TypeScript

These instructions guide Copilot to generate modern, accessible, type-safe, and maintainable React 19 code using TypeScript, following industry best practices and leveraging the latest React 19 features.

---

## ✅ General Project Standards

- Always use **TypeScript**, avoid untyped `.js` files.
- Follow **ESLint**, **Prettier**, and **TypeScript strict mode** configurations.
- Prefer functional components with **arrow functions**.
- Use **React 19 features**, including Actions, improved Server Components (if SSR used), and `useOptimistic`.
- Structure project folders logically:
  - `components/` - Reusable UI components
  - `hooks/` - Custom hooks
  - `services/` - API calls and business logic
  - `utils/` - Utility functions
  - `types/` - Shared TypeScript types

---

## ✅ React 19 Best Practices

- Use **Actions** for form submissions and server interactions in SSR/React Server Components setups.
- Leverage `useOptimistic` for optimistic UI updates where appropriate.
- Prefer **StrictMode** enabled for development.
- Use `useId()` to generate unique IDs when required.
- For SSR projects:
  - Use Server Components when applicable.
  - Keep Server/Client boundaries clear.
- Keep components **small**, **focused**, and **pure** where possible.
- Extract reusable logic into **custom hooks**.

---

## ✅ TypeScript Best Practices

- Enable `"strict": true` in `tsconfig.json`.
- Type all component props explicitly.
- Use `interface` or `type` consistently for defining props and complex structures.
- Avoid `any`; use `unknown` with type guards if needed.
- Leverage utility types like `Partial`, `Pick`, and `Record` as needed.
- Use **discriminated unions**, **enums**, and **literal types** where appropriate.
- Use default generic types for hooks like `useState<string>()`.

---

## ✅ Component Development

- Components must be:
  - Small and reusable.
  - Function components with arrow syntax.
  - Strictly typed with TypeScript.
- Keep logic minimal inside components; extract to hooks or services.
- Avoid unnecessary re-renders:
  - Use `React.memo` for pure presentational components.
  - Use `useCallback` and `useMemo` for expensive computations or handlers.
- Follow **accessibility (a11y)** standards:
  - Use semantic HTML.
  - Include ARIA attributes where needed.
  - Ensure keyboard navigability.
- Prefer **controlled components** for forms.
- Use `useId()` for generating stable, unique IDs.

---

## ✅ State & Data Management

- Prefer **local component state** with `useState` or `useReducer`.
- For shared state:
  - Use React Context sparingly for global, static state.
  - Consider **Zustand**, **Jotai**, or other minimal state management if required.
- Use `useOptimistic` for managing optimistic UI updates.
- Avoid prop drilling; extract shared state to proper boundaries.
- For data fetching:
  - Prefer `fetch` with `async/await`.
  - Use custom hooks to encapsulate fetching logic.
  - Consider libraries like **React Query** for complex async state.

---

## ✅ Styling Best Practices

- Prefer **CSS Modules**, **Tailwind CSS**, or **styled-components**.
- Avoid global styles except in `index.css` or global files.
- Maintain consistent theming and responsive design.
- Follow BEM or utility-based naming conventions for CSS classes.

---

## ✅ Testing Best Practices

- Use **Jest** and **React Testing Library** for component and logic testing.
- Write isolated, repeatable tests with clear assertions.
- Mock external services and dependencies where applicable.
- Include tests for:
  - Rendering.
  - User interactions.
  - State changes.
  - Accessibility (using `axe` or equivalent).
- Avoid testing implementation details; focus on behavior.
- Structure tests alongside components as `*.test.tsx` files or in `__tests__/`.

---

## ✅ Performance & Optimization

- Use `React.memo` for pure, non-changing components.
- Use `useCallback` and `useMemo` to memoize expensive operations.
- Code-split large components with `React.lazy` and `Suspense`.
- Prefer event delegation over individual event handlers where possible.
- Avoid unnecessary state updates.

---

## ✅ Accessibility & UX

- All interactive elements (buttons, links, inputs) must be accessible.
- Use semantic HTML tags.
- Include `aria-*` attributes where needed.
- Ensure proper keyboard navigation.
- Provide visible focus indicators.
- Use `useId()` to link inputs with labels/accessibility attributes.

---

## ✅ Code Quality & Maintainability

- Follow **SOLID**, **DRY**, and **KISS** principles.
- Avoid code duplication.
- Document complex logic with comments or `README.md` in relevant folders.
- Co-locate files logically by feature or component.
- Maintain consistent code style enforced by linters and formatters.
- Use absolute imports with `tsconfig.paths` where appropriate.

---

## ✅ Additional Copilot Behavior Preferences

When generating code:

- Assume **React 19** project structure and latest features.
- Suggest **TypeScript-typed**, modern React 19 functional components.
- Prefer readable, maintainable, and accessible code over clever shortcuts.
- Recommend tests alongside new components or logic.
- Suggest accessibility improvements (ARIA, semantic tags).
- Avoid outdated class components, legacy patterns, and untyped code.
- Leverage new React 19 features like Actions and `useOptimistic`.
