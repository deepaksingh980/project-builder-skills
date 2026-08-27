# Example: SaaS Platform Walkthrough

## Raw Scope Input
```text
"Build a multi-tenant SaaS analytics platform where team admins invite members, choose monthly billing tiers (Starter, Pro, Enterprise), view usage analytics dashboards, and manage API keys."
```

## Transformation Pipeline

### 1. Scope Normalization
- **Actors**: Team Admin, Team Member, Super Admin.
- **Entities**: `Tenant/Organization`, `User`, `Subscription`, `ApiKey`, `AnalyticsEvent`.
- **Modules**: Auth & Multi-Tenancy, Team Management, Billing & Tier Enforcement, Analytics Dashboard, API Key Management.

### 2. Architecture & Security Gate
- Enforce tenant isolation (`tenant_id` scope enforced on ALL SQL queries and API endpoints).
- Implement RBAC (Admin vs Member privileges).
- Tier enforcement middleware restricting features based on active subscription status.

### 3. Generated Memory Files
- Full `.antigravity/` suite created and maintained across 14 dependency-aware tasks.

### 4. Verification & Audit
- OWASP security scan verifying tenant data boundary isolation and API key hashing.
- Complete 20-point production readiness check passed.
