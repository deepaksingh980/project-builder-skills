# Universal Coding Standards

## 1. Type Safety & Explicit Contracts
- **Strict TypeScript**: Avoid `any` types. Use explicit interfaces, types, generics, and enums.
- **Null Safety**: Handle optional properties explicitly with optional chaining (`?.`) and nullish coalescing (`??`).
- **No Type Assertion Hacks**: Avoid `as any` or `@ts-ignore` to suppress compilation warnings. Fix the underlying interface contract.

## 2. Code Organization & Modularity
- **Single Responsibility Principle (SRP)**: Keep functions and components small, focused, and cohesive.
- **File Naming Conventions**: Use consistent naming (e.g. `user.service.ts`, `user.controller.ts`, `UserCard.tsx`).
- **Explicit Imports**: Use clean module aliases (e.g. `@/components`, `@/services`) instead of long relative paths (`../../../`).

## 3. Error Handling Protocol
- **Explicit Exceptions**: Throw custom domain error classes with standard HTTP status codes.
- **Global Error Middleware**: Catch unhandled exceptions at the API entry point and transform into standardized JSON error responses.
- **Zero Silent Catches**: Never write empty `catch (e) {}` blocks. Log or rethrow errors appropriately.

## 4. Documentation & Comments
- **Self-Documenting Code**: Choose clear, descriptive variable and function names.
- **Preserve Existing Comments**: Retain existing docstrings and comments when refactoring unless directly modified.
