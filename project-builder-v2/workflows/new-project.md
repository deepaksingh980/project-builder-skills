# Workflow: Greenfield New Project (`new-project`)

This workflow defines the complete step-by-step procedure for initializing and building a new software application from a raw natural-language prompt.

---

## 🎯 Phase 1 — Scope Ingestion & Normalization

1. **Ingest Prompt**: Accept input in English, Hindi, Hinglish, or client language text.
2. **Role Mapping**: Identify system actors (e.g. Owner, Renter, Admin, Support).
3. **Module Breakdown**: Decompose scope into core functional modules (e.g. Auth, Property Management, Booking Engine, Subscriptions, Admin Console).
4. **Requirement Categorization**:
   - *Explicit Requirements*: Hard requirements directly stated by user.
   - *Safe Assumptions*: Industry standard sensible choices (JWT auth, pagination, responsive UI).
   - *Critical Unknowns*: High-impact questions (e.g. choice of payment gateway if unstated).
5. **Initialize Project Memory**: Create `.antigravity/` directory with templates:
   - `project-profile.md`
   - `project-state.md`
   - `requirements.md`

---

## 📐 Phase 2 — Architecture & Design Blueprinting

1. **Stack Selection**: If unspecified, analyze project requirements and choose optimal tech stack (e.g., Next.js + React + Node + Prisma/PostgreSQL + TypeScript). Document rationale in `.antigravity/project-profile.md`.
2. **System Architecture**: Define module boundaries, data flow, external integrations in `.antigravity/architecture.md`.
3. **Database Schema Design**: Draft ER model, entity relationships, fields, constraints, unique keys, and indexes in `.antigravity/database.md`.
4. **API Specification**: Standardize REST/GraphQL endpoints, request/response bodies, pagination, and error contracts in `.antigravity/api-contracts.md`.
5. **UI/UX Strategy**: Map screen hierarchy, routes, responsive layouts, design system tokens, and 5 UI states (Default, Loading, Empty, Error, Disabled) in `.antigravity/ui-plan.md`.

---

## 📋 Phase 3 — Task Generation & Dependency Graph

1. **Decompose Requirements into Atomic Tasks**:
   - Foundation & Setup (Repo init, dependencies, linters, env setup)
   - Database Models & Migrations
   - Authentication & RBAC Middleware
   - Core API Modules (Vertical Slices)
   - Frontend Layout, Router & Global Components
   - Feature Screen Implementations
   - Integrations & Notifications
   - Automated Testing Suite
   - Security Audit & Production Hardening
2. **Build Dependency Graph**: Assign prerequisite task IDs to enforce execution order.
3. **Write to Task Memory**: Store in `.antigravity/task-plan.md` with status `PENDING`.

---

## 🔄 Phase 4 — Autonomous Execution Loop

For each task in `task-plan.md`:

```
┌──────────────────────────────────────────────────────────┐
│ 1. Select Next Task (Dependencies == COMPLETED)          │
└──────────────────────────┬───────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────┐
│ 2. Read Relevant Specifications & Code Context           │
└──────────────────────────┬───────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────┐
│ 3. Implement Code / Component / Endpoint / Migration      │
└──────────────────────────┬───────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────┐
│ 4. Run Targeted Verification (Typecheck, Lint, Test)     │
└──────────────────────────┬───────────────────────────────┘
                           │
                 Does check pass?
                ├── NO  ──► Capture Error → Diagnose Root Cause → Apply Minimal Fix → Retry Check
                └── YES ──► Mark Task COMPLETED → Log in changelog.md → Proceed to Next Task
```

---

## 🔒 Phase 5 — Quality, Security & UX Gates

1. **Security Gate**: Verify server-side authorization on all routes, check OWASP Top 10, scan for hardcoded secrets, check CORS and cookie security.
2. **UX Gate**: Test responsive layouts at Desktop (1440px), Tablet (768px), and Mobile (375px) viewports. Ensure loading, empty, and error states are present.
3. **Testing Gate**: Execute full test suite (`npm test` or framework equivalent). Ensure all happy paths and key error cases pass.

---

## 🏁 Phase 6 — Production Verification & Handover

1. Execute full production build check (`npm run build`).
2. Verify zero TypeScript errors and zero linter warnings.
3. Complete the 20-Point Production Readiness Checklist in `.antigravity/production-audit.md`.
4. Generate final delivery summary in prompt response.
