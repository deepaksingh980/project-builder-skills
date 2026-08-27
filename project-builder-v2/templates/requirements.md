# Requirements Specification & Traceability Matrix

## System Actors & Roles
- **Guest**: Unauthenticated visitor.
- **Registered User / Customer**: Standard user.
- **Owner / Provider**: Resource list owner.
- **Administrator**: System manager.

## Functional Requirements

| Requirement ID | Module | Description | Explicit / Inferred | Status |
| :--- | :--- | :--- | :--- | :--- |
| `REQ-AUTH-001` | Auth | User registration with email/password validation | Explicit | PENDING |
| `REQ-AUTH-002` | Auth | User login issuing JWT access token & HTTP cookie | Explicit | PENDING |
| `REQ-PROP-001` | Property | Property owners can create, edit, and publish listings | Explicit | PENDING |
| `REQ-SUB-001`  | Billing  | Owners can select and pay for monthly subscription plans | Explicit | PENDING |

## Non-Functional Requirements (NFRs)
- **NFR-SEC-001**: Server-side RBAC enforcement on all protected routes.
- **NFR-PERF-001**: API response times under 200ms for standard queries.
- **NFR-UX-001**: Responsive layout supporting Mobile, Tablet, and Desktop.
