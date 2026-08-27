# Automated Testing Standards

## 1. Testing Pyramid & Strategy
- **Unit Tests**: Test pure business logic, calculations, data formatters, and utility functions.
- **Integration Tests**: Test API controllers, database queries, authentication flows, and validation middleware.
- **E2E / Smoke Tests**: Test critical multi-step user workflows (e.g. registration $\rightarrow$ login $\rightarrow$ booking $\rightarrow$ payment confirmation).

## 2. Assertion Quality & Edge Case Coverage
Test suites MUST cover:
1. **Happy Paths**: Standard expected usage.
2. **Input Validation Failures**: Invalid email, short password, negative amounts, out-of-range dates.
3. **Authorization Gate Rejections**: Unauthenticated requests, unauthorized role access.
4. **Boundary / Edge Conditions**: Empty arrays, null values, concurrent requests.

## 3. Test File Conventions
- Unit/Integration tests: Colocated in `__tests__/` or named `<filename>.test.ts`.
- Mock external services (e.g. Stripe, AWS S3, SendGrid) in unit tests using clean mock interfaces.

## 4. No Workaround Policy
- Tests must pass cleanly without skipping or disabling assertions.
- Skipping or commenting out tests to force CI pass is strictly prohibited.
