# API Contracts Specification

## Base URL
`/api/v1`

## Standard Envelope Format
```json
{
  "success": true,
  "data": {},
  "error": null
}
```

## Endpoints

### 1. Authentication
- **`POST /api/v1/auth/register`**
  - Request Body: `{ email, password, role }`
  - Response: `{ success: true, data: { user, token } }`
- **`POST /api/v1/auth/login`**
  - Request Body: `{ email, password }`
  - Response: `{ success: true, data: { user, token } }`

### 2. Properties / Resource Management
- **`GET /api/v1/properties`**
  - Query Params: `page`, `limit`, `city`, `minPrice`, `maxPrice`
  - Response: `{ success: true, data: [ ... ], meta: { page, limit, total } }`
- **`POST /api/v1/properties`**
  - Headers: `Authorization: Bearer <token>`
  - Request Body: `{ title, description, price_per_night, location }`
  - Response: `{ success: true, data: { property } }`
