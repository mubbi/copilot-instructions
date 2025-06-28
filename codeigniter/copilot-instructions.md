# GitHub Copilot Custom Instructions for CodeIgniter 4.6 with PHP 8.4

These instructions guide Copilot to generate clean, modern PHP code aligned with **CodeIgniter 4.6+** structure, leveraging **PHP 8.4** features and following software engineering best practices for maintainability, testability, and security.

---

## ✅ General Coding Standards

- Use `declare(strict_types=1);` at the top of all PHP files.
- Follow **PSR-12** coding style and naming conventions.
- Write **small, focused classes and methods** (Single Responsibility Principle).
- Use **meaningful, descriptive names** for variables, methods, classes, and files.
- Include **PHPDoc** for all public classes and methods.
- Avoid magic numbers and hardcoded values — use class constants or config files.
- Prefer **early returns** and guard clauses for readability.

---

## ✅ PHP 8.4 Features & Best Practices

- Use **readonly properties** for immutable objects.
- Use **readonly classes** where immutability is intended throughout.
- Use **Enums** for predefined states or types (e.g., status, roles).
- Leverage **true/false standalone types** in return type declarations.
- Use **Constructor Property Promotion** for brevity.
- Apply **First-class callable syntax** for clean callbacks.
- Use **Named arguments** for clarity when calling methods with multiple optional parameters.
- Use the **Nullsafe operator (?->)** for optional chains.
- Apply **Union** and **Intersection Types** for stricter type safety.
- Mark utility classes or internal classes as **final** if extension is not intended.

---

## ✅ CodeIgniter 4.6+ Structure & Conventions

- Adhere to official CodeIgniter 4.6+ directory structure:
  - `app/Controllers` – Thin request handlers.
  - `app/Models` – Interact with the database using the Query Builder or Entities.
  - `app/Entities` – Use for structured data representation with accessors/mutators.
  - `app/Services` – Core business logic or application services.
  - `app/Libraries` – Reusable classes or helpers.
  - `app/Filters` – Middleware for request handling (auth, logging, etc.).
  - `app/Config` – Environment-specific config values.

- Controllers must:
  - Be **thin**, delegating logic to services/libraries.
  - Use **dependency injection** for services.
  - Use `ValidationInterface` for input validation.
  - Return `ResponseInterface` with proper status codes and content type.

- Use **View Cells** or **ViewModels** to isolate logic from view files.
- Avoid putting logic in view templates.

---

## ✅ Database, Models & Entities

- Use `BaseModel` with:
  - `$allowedFields` for mass assignment protection.
  - `returnType` set to custom `Entity` where appropriate.
  - Built-in support for timestamps and soft deletes.
- Write migrations for all schema changes:
  - Add appropriate constraints and indexes.
  - Prefer `UUID` or `ULID` where global uniqueness is needed.
- Use `Entity` classes for object-oriented representation of table rows.

---

## ✅ API Development

- Use `setJSON()` or `respond()` from `APIController` to return consistent responses.
- Implement **versioned API routes** (e.g., `/api/v1/users`).
- Validate all input using `Validation` service or custom rules.
- Apply proper HTTP status codes (`200`, `201`, `400`, `422`, `500`, etc.).
- Use route filters for **authentication**, **rate limiting**, and **CORS**.

---

## ✅ Views

- Keep views logic-free; pass only pre-processed data from controllers.
- Use `View Cells` for reusable blocks with logic (e.g., sidebar, menu).
- Organize reusable layout sections with `extend()` and `section()`.

---

## ✅ Security Best Practices

- Use built-in **CSRF**, **CSP**, and **XSS** protection mechanisms.
- Validate and sanitize all inputs.
- Use prepared statements via the Query Builder to avoid SQL injection.
- Store secrets in `.env`, not in code.
- Apply role-based or permission-based access control using filters or custom guards.

---

## ✅ Testing Standards

- Use **PHPUnit** with CI4’s built-in test framework.
- Write **unit tests** for services, libraries, and helpers.
- Write **feature tests** for HTTP interactions and APIs.
- Use **factories** or **seeders** to create test data.
- Mock external APIs and services with CI4's service injection or `Mockery`.

---

## ✅ Software Quality & Maintainability

- Follow **SOLID**, **DRY**, **KISS**, and **YAGNI** principles.
- Use **interfaces** and **dependency injection** for extensibility.
- Write clean, modular code with minimal side effects.
- Document public APIs and complex logic using PHPDoc.

---

## ✅ Performance & Optimization

- Use **eager loading** to prevent N+1 query issues.
- Cache expensive operations with CI4’s caching system (file, Redis, etc.).
- Paginate large result sets using `paginate()`.
- Offload long-running tasks using queues (via 3rd-party packages).
- Optimize DB performance using proper indexes and query profiling.

---

## ✅ Modern CI4 Features to Use

- Use **Shield** for robust authentication and authorization.
- Use **custom CLI commands** for automation and tasks.
- Use **Events** to decouple logic from controllers.
- Use **View Cells** to structure view logic cleanly.
- Use **Config classes** instead of hardcoded values.

---

## ✅ Copilot Behavior Preferences

- Generate **strictly typed**, modern PHP 8.4 code.
- Default to **service classes**, **entities**, and **validation rules**.
- Suggest **tests** alongside business logic.
- Avoid deprecated or legacy CI3 patterns.
- Prioritize **clarity**, **security**, and **reusability** over clever hacks.
