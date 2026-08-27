# Workflow: 10-Point Project Audit (`audit` / `/audit`)

This workflow defines the execution protocol for evaluating an existing or newly completed project across 10 critical engineering dimensions.

---

## 📋 10-Point Audit Checklist

```
 1. Architecture Audit   ────────► Check modularity, layer leaks, circular deps
 2. Code Quality Audit   ────────► Check type safety, DRY principle, lint compliance
 3. Database Audit       ────────► Check schema normalization, indexes, soft deletes
 4. API Audit            ────────► Check REST standards, error contracts, status codes
 5. Security Audit       ────────► Check OWASP Top 10, server-side RBAC, secrets
 6. Performance Audit    ────────► Check query efficiency, bundle size, caching
 7. Frontend/UX Audit    ────────► Check responsive breakpoints, 5 UI states
 8. Testing Audit        ────────► Check coverage, edge cases, assertion validity
 9. DevOps Config Audit  ────────► Check env variables, build scripts, dockerfiles
10. Requirement Coverage ────────► Trace original scope items to implementation
```

---

## 🔍 Execution Steps

1. Inspect source tree, configurations, schemas, API endpoints, tests, and `.antigravity/` project state.
2. Evaluate codebase against each of the 10 dimensions.
3. Categorize findings by severity:
   - `CRITICAL`: Immediate security vulnerability, data loss risk, or broken build.
   - `HIGH`: Major performance bottleneck, missing authorization gate, unhandled crash condition.
   - `MEDIUM`: Sub-optimal database query, missing index, incomplete UI loading state.
   - `LOW`: Code formatting minor inconsistency, missing inline comment, minor copy typo.
4. Generate structured report and save to `.antigravity/production-audit.md`.

*IMPORTANT: In AUDIT mode, do NOT modify application code unless explicitly requested by the user.*
