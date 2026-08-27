# Workflow: Production Readiness Gate (`production-readiness`)

This workflow defines the final verification checklist and gating mechanism required before declaring any software project fully `PRODUCTION READY`.

---

## 20-Point Production Readiness Checklist

### 1. Functional & Architecture Integrity
- [ ] **R-1 Requirements**: 100% of explicit functional requirements implemented.
- [ ] **R-2 Architecture**: Coherent layer separation (UI → Service → Data Access).
- [ ] **R-3 Data Integrity**: DB schemas indexed, constraints enforced, non-destructive migrations verified.
- [ ] **R-4 API Consistency**: Unified API response structure (`{ success, data, error }`) on all routes.

### 2. Security & Compliance
- [ ] **R-5 Authentication**: Strong password hashing, secure JWT / session token lifecycle.
- [ ] **R-6 Server-Side Authorization**: RBAC / ABAC enforced server-side on every protected endpoint.
- [ ] **R-7 Input Validation**: Sanitize and validate request bodies/params using schema validators.
- [ ] **R-8 Error Handling**: Global exception handler; zero unhandled promise rejections or raw stack traces returned to client.
- [ ] **R-9 Zero Hardcoded Secrets**: No secret keys, API credentials, or passwords committed to source control.
- [ ] **R-10 OWASP Hardening**: CORS configured, rate limiting enabled, secure cookies set, Helmet headers applied.

### 3. Build & Test Quality
- [ ] **R-11 Automated Tests**: Unit and integration test suites pass with 0 failures.
- [ ] **R-12 Type Safety**: TypeScript compiler check (`tsc --noEmit`) passes with 0 errors.
- [ ] **R-13 Code Quality**: Linter (`eslint` / `biome`) passes with 0 errors.
- [ ] **R-14 Production Build**: Bundle compilation (`npm run build`) completes cleanly.

### 4. UX & Frontend Excellence
- [ ] **R-15 Responsive Design**: Mobile (375px), Tablet (768px), and Desktop (1440px) verified.
- [ ] **R-16 Five UI States**: Default, Loading, Empty, Error, and Disabled states implemented on all interactive views.

### 5. Ops, Config & Documentation
- [ ] **R-17 Environment Config**: `.env.example` file provided with all required environment variable keys.
- [ ] **R-18 Structured Logging**: Logger configured to record production events without leaking PII or credentials.
- [ ] **R-19 Documentation**: Complete README with quickstart, API documentation, and deployment guides.
- [ ] **R-20 Requirement Traceability**: Requirement Traceability Matrix fully updated and verified.

---

## 🏁 Gate Execution Result

If all 20 checks pass, write `Status: PRODUCTION READY` in `.antigravity/production-audit.md` and present the Final Report to the user.
