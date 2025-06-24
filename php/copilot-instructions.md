# GitHub Copilot Custom Instructions for PHP 8.2/8.4 Projects

These instructions guide Copilot to generate modern, clean, secure, and maintainable PHP code for non-Laravel projects using PHP 8.2 or newer. Follow strict standards, leverage language features, and produce production-quality software.

---

## ✅ General PHP Coding Standards

- Always start files with `declare(strict_types=1);`.
- Follow **PSR-12** coding standards for formatting and structure.
- Prefer meaningful, descriptive variable, function, class, and file names.
- Structure projects with proper namespaces reflecting directory hierarchy.
- Avoid global functions and variables unless absolutely necessary.
- Use **type hints** and **return types** for all functions and methods.
- Apply **final** to classes and methods where extension is not intended.

---

## ✅ PHP 8.2/8.4 Language Features to Use

- Use **readonly properties** to enforce immutability where applicable.
- Use **Enums** instead of string or integer constants for fixed value sets.
- Leverage **First-class callable syntax** for passing functions (`$callback(...)`).
- Use **Constructor Property Promotion** for concise class constructors.
- Apply **Union Types**, **Intersection Types**, and **true/false return types** for stricter typing.
- Utilize **Static Return Type** where appropriate.
- Use the **Nullsafe Operator (?->)** for safe method/property access on nullable objects.
- Prefer **Named Arguments** for clarity in complex function calls.
- Embrace **anonymous classes** or **anonymous functions** when appropriate.
- Follow upcoming PHP 8.4 improvements, avoid deprecated features from older PHP versions.

---

## ✅ Project Structure & Organization

- Organize code using **PSR-4 autoloading** standards.
- Group files by logical responsibility (e.g., `src/Services`, `src/Models`, `src/Utils`).
- Keep files and classes small, following the **Single Responsibility Principle**.
- Prefer **interfaces** and **abstract classes** for contracts and shared logic.
- Separate concerns:
  - Business logic → Service classes
  - Data representation → Value Objects or DTOs
  - External API interactions → Dedicated API clients
  - Configuration → `.env` files or configuration classes

---

## ✅ Object-Oriented Best Practices

- Practice **encapsulation**: keep properties `private` or `protected`.
- Use **Dependency Injection**, avoid `new` inside classes unless necessary.
- Prefer immutability with `readonly` and immutable objects.
- Apply **Design Patterns** appropriately (e.g., Factory, Strategy, Adapter, Singleton if justified).
- Avoid overengineering or unnecessary abstraction.
- Document public methods with **PHPDoc**, especially for complex logic.

---

## ✅ Error Handling & Exceptions

- Always use exceptions for error handling.
- Catch and handle exceptions at appropriate layers, don't suppress errors silently.
- Create custom exception classes for domain-specific errors.
- Use `Throwable` or `Exception` type hints where applicable.

---

## ✅ Security Best Practices

- Never trust user input; always validate and sanitize input.
- Escape output for HTML, JSON, SQL, etc.
- Use **prepared statements** for all database interactions to prevent SQL injection.
- Store secrets in `.env` or configuration files, never hard-code them.
- Apply proper password hashing with `password_hash()` and `password_verify()`.
- Follow **principle of least privilege** for permissions.

---

## ✅ Testing & Quality Assurance

- Use **PHPUnit** for unit and integration testing.
- Write isolated, repeatable tests with clear assertions.
- Use **mocking** or **stubs** for external dependencies.
- Aim for meaningful test coverage focusing on critical business logic.
- Validate code style with tools like `PHP-CS-Fixer` or `PHP_CodeSniffer`.
- Run static analysis with tools like `PHPStan` or `Psalm`.

---

## ✅ Modern Development Practices

- Follow **SOLID Principles**:
  - Single Responsibility
  - Open/Closed
  - Liskov Substitution
  - Interface Segregation
  - Dependency Inversion

- Apply **DRY** (Don't Repeat Yourself) and **KISS** (Keep It Simple, Stupid).
- Avoid premature optimization; write readable, maintainable code first.
- Consider **YAGNI** (You Aren't Gonna Need It) to prevent unnecessary complexity.

---

## ✅ Performance & Efficiency

- Profile and optimize critical code paths when needed.
- Avoid unnecessary object creation inside loops.
- Prefer strict comparisons (`===`, `!==`) over loose comparisons.
- Cache expensive operations if applicable.

---

## ✅ Additional Copilot Behavior Preferences

When generating code:

- Always assume **strict typing** and modern PHP 8.2/8.4 usage.
- Prefer readability, clarity, and maintainability over clever shortcuts.
- Avoid legacy PHP patterns such as:
  - Global state
  - Magic methods misuse
  - Procedural code unless justified
- Suggest proper class placement within a logical project structure.
- Suggest unit tests alongside new functionality where applicable.
- Default to modern, secure, and best-practice-compliant approaches.
