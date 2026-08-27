# Workflow: State Continuation (`continue` / `/continue`)

This workflow defines how `project-builder-v2` recovers project context after terminal restarts, session drops, context compression, or multi-session implementation work.

---

## 📖 Phase 1 — Project Memory Ingestion

1. Check for existence of `.antigravity/` directory.
2. Read project context files:
   - Read `.antigravity/project-state.md` to identify current phase and active task.
   - Read `.antigravity/task-plan.md` to view completed vs pending tasks.
   - Read `.antigravity/project-profile.md` to understand tech stack, constraints, and architecture.

---

## 🔍 Phase 2 — Repository Reconciliation (Codebase vs State Check)

Do NOT blindly trust state files. Reconcile state against actual physical files on disk:

1. **Verify Files**: Confirm files associated with `COMPLETED` tasks actually exist.
2. **Verify Integrity**: Run quick typecheck (`npx tsc --noEmit` or equivalent) to confirm existing code compiles cleanly.
3. **Re-align Task Status**:
   - If a task marked `COMPLETED` has broken code, change status back to `IN_PROGRESS`.
   - If a task marked `IN_PROGRESS` was interrupted mid-way, inspect modified files and git status.

---

## 🚀 Phase 3 — Execution Resumption

1. Select the first `PENDING` task whose prerequisites are marked `COMPLETED`.
2. Update `.antigravity/project-state.md` with:
   - `Active Task: <Task ID>`
   - `Current Phase: IMPLEMENTATION`
3. Resume the Autonomous Development Loop seamlessly.
