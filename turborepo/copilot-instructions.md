# GitHub Copilot Custom Instructions for Turborepo-Based Monorepos

These instructions guide Copilot to generate code and configurations tailored for projects using **Turborepo**. They focus on modularity, reusability, type safety, performance, and clean architecture within a monorepo ecosystem.

---

## ✅ Monorepo Structure Guidelines

Follow a clean and consistent folder layout:

```
/apps
  ├── web        # Frontend app (Next.js, React, etc.)
  ├── admin      # Optional admin panel
  └── api        # Backend app (Node.js, NestJS, etc.)

/packages
  ├── ui         # Shared UI components (e.g., React components)
  ├── config     # Shared configuration (e.g., ESLint, Prettier, Tailwind)
  ├── tsconfig   # Shared TypeScript config
  └── utils      # Shared utilities (e.g., helpers, hooks)
```

---

## ✅ Code Generation Standards

- Prefer **TypeScript** over JavaScript for all projects.
- Use **ES Modules**.
- Structure each `package/` as a self-contained, reusable module.
- Use **absolute imports** via `tsconfig.paths`.
- Keep **apps thin** and delegate logic to shared packages.
- Always export reusable functions/components from shared packages.
- Keep logic **co-located** (e.g., hooks with components, utils with feature).

---

## ✅ TypeScript Configuration

- Use a root-level `tsconfig.json` that extends per-package configs:
```json
// tsconfig.json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@ui/*": ["packages/ui/src/*"],
      "@utils/*": ["packages/utils/src/*"]
    }
  }
}
```

- Make `tsconfig.base.json` and extend it across apps and packages.

---

## ✅ Linting & Formatting

- Use **ESLint** with shared rules under `packages/config/eslint`.
- Use **Prettier** and run it with Turborepo `lint` pipeline.
- Example package.json script:
```json
"scripts": {
  "lint": "turbo run lint",
  "format": "prettier --write ."
}
```

---

## ✅ Package Management

- Use **pnpm workspaces** or **npm/yarn workspaces**.
- Define your workspace root in `package.json`:
```json
"workspaces": [
  "apps/*",
  "packages/*"
]
```

- Avoid circular dependencies.
- Use consistent versions across packages via `devDependencies`.

---

## ✅ Build & Pipeline Strategy

- Use `turbo.json` to define pipelines:
```json
{
  "pipeline": {
    "build": {
      "dependsOn": ["^build"],
      "outputs": ["dist/**"]
    },
    "lint": {},
    "test": {}
  }
}
```

- Keep `outputs` configured for caching and faster CI builds.
- Run tasks in parallel unless dependent.

---

## ✅ Testing Practices

- Prefer **Vitest** or **Jest** with shared config under `/packages/config`.
- Keep test files close to source code (`*.test.ts`).
- Use **MSW** or mocks for API calls in frontend apps.
- Share mocks and test helpers in `packages/test-utils`.

---

## ✅ App & Package Isolation

- Treat each app and package as **independent**, with clear interfaces.
- Avoid tightly coupling apps to shared packages.
- Use **strict versioning** and CI checks to maintain modularity.

---

## ✅ Copilot Behavior Preferences

- Generate reusable components and utilities inside `packages/` directories.
- Prefer **typed functions**, **hook-based state**, and **co-located logic**.
- Avoid hardcoded config duplication — use shared config packages.
- Suggest **test stubs** and types when creating new packages.
- Recommend `turbo run` commands for running scripts efficiently.

---

## ✅ Optional Tech Stack Guidance

If used, prefer the following stack integrations:
- Frontend: Next.js, Tailwind, React, Radix UI, shadcn/ui
- Backend: tRPC, Express, or NestJS
- Auth: NextAuth.js, Clerk, Auth.js
- State: React Query, Zustand, or Context API
- Deployments: Vercel, AWS, Cloudflare
