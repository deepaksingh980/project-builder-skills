# Workflow: Feature Development (`feature-development` / `/feature`)

This workflow defines the procedure for adding new functional modules or capabilities to a project while maintaining zero-regression safety for existing code.

---

## 🎯 Phase 1 — Feature Specification & Scoping

1. **Parse Feature Request**: Extract feature goal, target user role, required UI screens, API endpoints, and database models.
2. **Update Requirements Matrix**: Append new feature requirements to `.antigravity/requirements.md` with unique IDs (e.g. `FEAT-SUB-001`).
3. **Architecture Impact Review**:
   - Update `.antigravity/architecture.md` with new module boundaries.
   - Design DB schema additions in `.antigravity/database.md` (ensuring non-destructive add operations).
   - Define new API contracts in `.antigravity/api-contracts.md`.
   - Update UI screen routes and component plans in `.antigravity/ui-plan.md`.

---

## 📋 Phase 2 — Task Breakdown & Scheduling

1. Generate atomic sub-tasks for the feature:
   - DB Schema migration & model creation
   - Backend service logic & controller/route endpoints
   - Request validation schema & RBAC middleware integration
   - Frontend UI components, forms, and views
   - State management integration & API service hooks
   - Unit & integration tests for the feature
2. Add tasks to `.antigravity/task-plan.md` under a dedicated Feature Section.

---

## 💻 Phase 3 — Vertical Slice Implementation

Implement feature layer by layer:

1. **Database Layer**: Add new tables/columns or Prisma/TypeORM migrations. Verify migration cleanly applies.
2. **Backend Service & API Layer**: Implement business logic, write input validation, enforce authorization, add API endpoints.
3. **Frontend UI Layer**: Build responsive UI components using design tokens, integrate form handling with 5 UI states (Default, Loading, Empty, Error, Disabled).
4. **Integration Layer**: Wire frontend API hooks to backend endpoints.

---

## 🧪 Phase 4 — Testing & Regression Verification

1. Write unit tests for new feature services and utility functions.
2. Write integration tests for new API endpoints.
3. Run existing full test suite to guarantee zero regression on previous features.
4. Update `.antigravity/qa-report.md` with new feature test results.
5. Record completion in `.antigravity/changelog.md`.
