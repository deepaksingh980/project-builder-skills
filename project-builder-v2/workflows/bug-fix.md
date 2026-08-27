# Workflow: Bug Fixing & Root-Cause Diagnosis (`bug-fix` / `/fix`)

This workflow defines the systematic, disciplined protocol for diagnosing, fixing, and verifying software defects, build errors, type failures, or runtime crashes without introducing hacky workarounds.

---

## 🐞 Phase 1 — Bug Capture & Reproduction

1. **Capture Error Output**:
   - Collect exact command output, stack traces, HTTP status codes, or failing test output.
   - Do NOT guess root cause before viewing full un-truncated error logs.
2. **Isolate Reproduction Case**:
   - Identify affected module, function, or API endpoint.
   - Determine precise trigger conditions (e.g. invalid date format, missing null check, un-authenticated request).

---

## 🔍 Phase 2 — Root Cause Analysis (RCA)

1. Inspect source files associated with stack trace frame by frame using code viewing tools.
2. Check upstream data providers, schema definitions, and contract mismatches.
3. Classify root cause:
   - *Type Error / Interface Mismatch*
   - *Unhandled Edge Case / Null Dereference*
   - *Database Schema / Query Constraint Failure*
   - *Authorization / Token Expiry Defect*
   - *Frontend State Synchronization Defect*

---

## 🛠️ Phase 3 — Minimal Robust Fix Execution

1. Formulate the smallest, most robust fix that addresses the root cause directly.
2. **FORBIDDEN QUICK-FIXES**:
   - ❌ Do NOT suppress TypeScript compiler with `@ts-ignore` or `any`.
   - ❌ Do NOT disable linter rules or comment out broken tests.
   - ❌ Do NOT wrap code in silent `try { ... } catch (e) {}` blocks that swallow errors.
   - ❌ Do NOT bypass authentication or server-side authorization checks.
3. Apply fix to target file(s).

---

## 🧪 Phase 4 — Regression Test & Verification

1. Write a targeted regression test that specifically reproduces the original bug condition and asserts the correct behavior.
2. Run targeted test to verify fix PASSES.
3. Run full project test suite to verify no collateral breakage occurred.
4. Record RCA, Fix Summary, and Regression Test in `.antigravity/changelog.md`.
