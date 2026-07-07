# Post-Purchase Address Validation

An end-to-end workflow automation that validates customer shipping addresses immediately after an order is placed. The workflow uses the Google Address Validation API to verify, standardize, and geocode addresses, stores every validation result in PostgreSQL for auditing, routes verified orders to the warehouse, and sends Slack notifications when manual review is required. A lightweight dashboard provides real-time visibility into validation status, confidence scores, corrected addresses, and warehouse operations.

---

## Features

- Shopify order trigger (`orders/paid`)
- Google Address Validation API integration
- Automatic address standardization
- Confidence score calculation
- Validation status classification
- PostgreSQL order storage
- Validation audit logging
- Warehouse API integration
- Slack notifications
- Real-time HTML dashboard
- Geocoding and Place ID storage
- Complete validation history

---

## Tech Stack

- n8n
- Shopify
- PostgreSQL
- Google Address Validation API
- Slack
- HTML
- JavaScript

---

## Workflow

```
Shopify Order Paid
        │
        ▼
Extract Order Details
        │
        ▼
Store Order
        │
        ▼
Validate Address
        │
        ▼
Calculate Validation Status
        │
        ├──────────────┐
        │              │
        ▼              ▼
Manual Review     Warehouse API
   (Slack)              │
        │               ▼
        └──────► Update Database
                        │
                        ▼
                 Dashboard API
                        │
                        ▼
                 HTML Dashboard
```

---

## Validation Status

| Status | Description |
|---------|-------------|
| READY | Address validated successfully |
| READY_WITH_CORRECTIONS | Google corrected one or more address components |
| REVIEW_REQUIRED | Address requires manual review before fulfillment |

---


## Dashboard

The dashboard provides:

- Total Orders
- Validation Status Summary
- Confidence Scores
- Original vs Corrected Addresses
- Geocoded Coordinates
- Warehouse Status
- Order Audit Trail

---

## Database

### orders

Stores customer, order, shipping, and warehouse information.

### address_validation_log

Stores:

- Original address
- Corrected address
- Google validation response
- Confidence score
- Geocode
- Place ID
- Validation history

---

## Use Cases

- Shopify Fulfillment Automation
- Warehouse Operations
- Address Verification
- Shipping Error Prevention
- Order Quality Control
- Operations Monitoring

---

## License

This project is licensed under the MIT License.
