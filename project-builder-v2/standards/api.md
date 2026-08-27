# API Standards & Contracts

## 1. RESTful URL Naming
- Use plural nouns for resources (e.g. `/api/v1/properties`, `/api/v1/users`).
- Use nested routes for child resources (e.g. `/api/v1/properties/:id/reviews`).
- HTTP Verbs: `GET` (Read), `POST` (Create), `PUT` / `PATCH` (Update), `DELETE` (Remove).

## 2. Standardized Response Format

### Success Response (HTTP 200 / 201)
```json
{
  "success": true,
  "data": { ... },
  "meta": {
    "page": 1,
    "limit": 10,
    "total": 45
  }
}
```

### Error Response (HTTP 4xx / 5xx)
```json
{
  "success": false,
  "error": {
    "code": "UNAUTHORIZED_ACCESS",
    "message": "You do not have permission to modify this property.",
    "details": []
  }
}
```

## 3. Query Parameters Strategy
- **Pagination**: `page` (default 1), `limit` (default 10, max 100).
- **Sorting**: `sortBy` (field name), `order` (`asc` | `desc`).
- **Filtering**: Clear field key queries (e.g. `status=AVAILABLE&city=Mumbai`).

## 4. Input Validation & Authorization
- Validate all incoming request payload schemas using validation middleware before reaching controller logic.
- Verify authorization claims server-side on every protected endpoint.
