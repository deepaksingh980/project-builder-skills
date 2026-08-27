# Example: Simple CRUD Application Walkthrough

## Raw Scope Input
```text
"Build a simple task management app where users can create tasks, mark them as completed, set due dates, and filter tasks by status."
```

## Transformation Pipeline

### 1. Scope Normalization
- **Actors**: Registered User.
- **Entities**: `Task` (id, user_id, title, description, due_date, status, created_at, updated_at).
- **Modules**: Auth, Task Manager.

### 2. Stack Recommendation
- **Frontend**: Vite + React + TypeScript + TailwindCSS.
- **Backend**: Express + TypeScript + Prisma ORM + PostgreSQL.

### 3. Generated Artifacts
- `.antigravity/project-profile.md`
- `.antigravity/requirements.md`
- `.antigravity/database.md`
- `.antigravity/api-contracts.md`
- `.antigravity/task-plan.md`

### 4. Implementation Loop
1. Setup repo & install packages (`express`, `prisma`, `react`, `zod`).
2. Run database migration for `Task` schema.
3. Build API endpoints (`GET /tasks`, `POST /tasks`, `PATCH /tasks/:id`, `DELETE /tasks/:id`).
4. Build responsive UI with 5 UI states (Loading skeleton, Empty task list graphic, Form validation, Error alert, Submitting state).
5. Run unit & integration tests (`npx jest`).
6. Run production build check (`npm run build`).
