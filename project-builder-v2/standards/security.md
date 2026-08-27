# Security Engineering Standards (OWASP Top 10)

## 1. Authentication & Session Security
- **Password Hashing**: Use bcrypt (cost factor $\ge 12$) or Argon2id. Never store plain text passwords.
- **JWT Handling**: Short-lived access tokens (e.g. 15 minutes) stored securely; refresh tokens in HTTP-only, secure, `SameSite=Strict` cookies.

## 2. Server-Side Authorization & RBAC
- Enforce role-based access control (RBAC) on the server for EVERY protected route.
- **IDOR Prevention**: Verify that the authenticated user owns the resource being accessed/modified (`req.user.id === resource.owner_id` or user has `ADMIN` role).

## 3. Input Sanitization & Injection Defense
- **SQL Injection**: Use parameterized queries or ORMs (Prisma, TypeORM, Drizzle). Never concatenate string inputs into raw SQL statements.
- **XSS Defense**: Escape output, sanitize HTML inputs, enforce Content Security Policy (CSP) headers.

## 4. Secret & Credentials Management
- Zero hardcoded API keys, DB passwords, or tokens in source code or git history.
- Use `.env` variables locally and environment secret managers in production.
- Provide a clear `.env.example` file with placeholder values.

## 5. Security Headers & CORS
- Use `helmet` middleware to set `X-Frame-Options`, `X-Content-Type-Options`, `Strict-Transport-Security`.
- Configure restrictive CORS origins instead of wildcard `*` in production configurations.
