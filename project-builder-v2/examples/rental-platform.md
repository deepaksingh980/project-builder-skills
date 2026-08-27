# Example: Rental Platform Walkthrough

## Raw Scope Input
```text
"Build a rental platform where owners can list properties, customers can rent them, subscriptions are available, admins can manage everything."
```

## Transformation Pipeline

### 1. Scope Normalization
- **Actors**:
  - `Owner`: List properties, manage availability calendars, view rental earnings, pay subscription fees.
  - `Renter / Customer`: Search properties by city/price, select dates, request bookings, pay rental fees.
  - `Admin`: Approve property listings, moderate users, view platform metrics, manage subscription tiers.
- **Modules**:
  1. `Auth & RBAC`: Registration, login, JWT issuing, role permissions (`OWNER`, `RENTER`, `ADMIN`).
  2. `Property Management`: CRUD endpoints for property title, description, amenities, location, price per night, image uploads.
  3. `Booking Engine`: Date range picker, availability checker (prevent overlapping bookings), reservation checkout.
  4. `Subscriptions`: Monthly owner subscription plans (Basic, Premium, Enterprise).
  5. `Admin Dashboard`: Analytics, listing approvals, user status toggle.

### 2. Architecture & Database Design
- Tables: `users`, `properties`, `property_images`, `bookings`, `subscriptions`, `reviews`.
- Indexes: `properties(owner_id)`, `properties(status, city)`, `bookings(property_id, start_date, end_date)`.

### 3. Execution & Verification Loop
- Generate task plan (`TASK-001` through `TASK-012`).
- Implement vertical slices layer by layer.
- Run automated unit tests for booking collision algorithm.
- Verify 5 UI states on property search view (Loading skeleton, Empty city results, Form submitting state, Error toast, Default card grid).
- Complete 20-point Production Readiness Gate audit.
