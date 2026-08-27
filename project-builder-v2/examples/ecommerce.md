# Example: Multi-Vendor E-Commerce Walkthrough

## Raw Scope Input
```text
"Build an e-commerce platform where vendors list products, customers browse and add items to a cart, checkout with Stripe payments, and track order fulfillment status."
```

## Transformation Pipeline

### 1. Scope Normalization
- **Actors**: Buyer, Vendor, Admin.
- **Entities**: `User`, `Store`, `Product`, `Category`, `Order`, `OrderItem`, `Payment`.
- **Modules**: Catalog & Search, Cart & Inventory Locking, Payment Gateway Integration, Order Lifecycle Management, Vendor Payouts.

### 2. Architecture & Data Flow
- Inventory race-condition handling during checkout using database transactions.
- Webhook listener verifying Stripe payment events before marking orders `PAID`.
- Unified error handling for card decline and out-of-stock scenarios.

### 3. Verification & Handover
- E2E checkout test verifying price calculations, tax addition, and order record creation.
- 10-point audit log saved to `.antigravity/production-audit.md`.
