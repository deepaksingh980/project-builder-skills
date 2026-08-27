# Database Standards

- Use migrations for schema changes when supported.
- Preserve existing data.
- Add constraints for important invariants.
- Add indexes based on real query patterns.
- Avoid N+1 query patterns.
- Use transactions for multi-step state changes when required.
