# Database Engineering Standards

## 1. Schema Conventions
- Table names: plural `snake_case` (e.g. `property_listings`, `user_subscriptions`).
- Column names: singular `snake_case` (e.g. `user_id`, `created_at`, `is_published`).
- Foreign keys: `<singular_entity>_id` with explicit foreign key constraints and `ON DELETE` behavior defined.

## 2. Standard Audit & Lifecycle Fields
Every primary database table MUST include:
- `id`: UUID (v4) or auto-incrementing BigInt primary key.
- `created_at`: Timestamp with timezone (default `NOW()`).
- `updated_at`: Timestamp with timezone (auto-updated).
- `is_active`: Boolean flag (default `true`).
- `deleted_at`: Optional timestamp for soft-deletion.

## 3. Indexing Guidelines
- Add explicit indexes on all foreign key columns.
- Add unique indexes on unique business keys (e.g. `email`, `slug`).
- Add composite indexes for common multi-column search queries.

## 4. Migration & Safety Rules
- **Non-Destructive Migrations**: Never execute `DROP TABLE`, `TRUNCATE`, or column deletion on existing projects without explicit user approval.
- Use versioned migration files (`0001_create_users.sql`, `0002_add_subscriptions.sql`).
- Test rollback and forward migration steps locally before applying to production environments.
