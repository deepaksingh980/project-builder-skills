# Security Standards

Never:
- hard-code secrets
- trust client authorization
- log passwords/tokens
- bypass validation to make a test pass
- disable security controls without explicit reason

Always consider authorization at the actual data access boundary.
