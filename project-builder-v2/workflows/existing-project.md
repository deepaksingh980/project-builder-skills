# Workflow: Existing Project Onboarding & Modification (`existing-project`)

This workflow defines how `project-builder-v2` safely inspects, analyzes, and modifies an existing codebase (brownfield project) without breaking existing functionality or violating existing conventions.

---

## 🔍 Phase 1 — Repository Inspection & Context Discovery

Before editing any code in an existing repository, perform comprehensive inspection:

1. **Package Manifest Analysis**:
   - Inspect `package.json`, `Cargo.toml`, `pyproject.toml`, `go.mod`, or `pom.xml`.
   - Identify framework versions, routing libraries, database ORMs, state management, and test runners.
   - Detect package manager (npm, yarn, pnpm, bun) from lockfiles (`pnpm-lock.yaml`, `yarn.lock`, `package-lock.json`).

2. **Directory & Architecture Mapping**:
   - Inspect source folder structure (`src/`, `app/`, `pages/`, `components/`, `server/`, `services/`).
   - Identify existing architectural patterns (MVC, Clean Architecture, Feature Folders, Monorepo).

3. **Coding Convention Extraction**:
   - Analyze linter configs (`.eslintrc`, `biome.json`, `prettierrc`).
   - Observe naming conventions (camelCase vs snake_case, interface naming, file naming).
   - Locate test patterns (`*.test.ts`, `*.spec.tsx`, `tests/`).

4. **Environment & Secret Discovery**:
   - Check `.env.example` to understand expected environment variables.
   - **SAFETY**: Never print, log, or commit values from `.env` or secret configuration files.

---

## 📝 Phase 2 — Project Memory Synchronization

1. Initialize or update `.antigravity/` project state files:
   - Extract current stack into `project-profile.md`.
   - Document existing database schema in `database.md`.
   - Document existing API endpoints in `api-contracts.md`.
   - Record current project state in `project-state.md`.

---

## 🛠️ Phase 3 — Change Impact Analysis

When tasked with modifying an existing codebase:

1. **Identify Affected Modules**: Map proposed changes to existing files, components, models, and endpoints.
2. **Backwards Compatibility Check**:
   - Ensure existing DB tables/columns are not destroyed.
   - Ensure existing API contracts remain valid or migration/versioning strategy is defined.
   - Ensure existing frontend components do not experience breaking prop changes.
3. **Regression Test Baseline**: Run existing test suite (`npm test`) before making changes to establish baseline test status.

---

## 🔄 Phase 4 — Incremental Modification Loop

1. Make minimal, surgical modifications following existing repo style.
2. Avoid re-formatting unrelated files or making sweeping style changes.
3. Preserve existing docstrings, comments, and non-conflicting logic.
4. Run targeted tests for modified modules.
5. Fix any regression immediately before marking task completed.
