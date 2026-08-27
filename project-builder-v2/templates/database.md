# Database Schema & Entity Design

## ER Diagram Summary
- `users` (1) ───< `properties` (N)
- `properties` (1) ───< `bookings` (N)
- `users` (1) ───< `subscriptions` (N)

## Entities Specification

### Table: `users`
| Column | Type | Constraints | Index |
| :--- | :--- | :--- | :--- |
| `id` | UUID | PRIMARY KEY | YES |
| `email` | VARCHAR(255) | UNIQUE, NOT NULL | YES |
| `password_hash` | VARCHAR(255) | NOT NULL | NO |
| `role` | VARCHAR(50) | DEFAULT 'CUSTOMER' | YES |
| `created_at` | TIMESTAMP | DEFAULT NOW() | NO |
| `updated_at` | TIMESTAMP | DEFAULT NOW() | NO |

### Table: `properties`
| Column | Type | Constraints | Index |
| :--- | :--- | :--- | :--- |
| `id` | UUID | PRIMARY KEY | YES |
| `owner_id` | UUID | FK -> users(id), NOT NULL | YES |
| `title` | VARCHAR(255) | NOT NULL | NO |
| `price_per_night` | DECIMAL(10,2) | NOT NULL | YES |
| `status` | VARCHAR(50) | DEFAULT 'DRAFT' | YES |
| `created_at` | TIMESTAMP | DEFAULT NOW() | NO |
| `updated_at` | TIMESTAMP | DEFAULT NOW() | NO |

## Migration Strategy
- Use non-destructive, versioned database migrations.
- Verify migrations apply cleanly in local dev environment before locking schema.
