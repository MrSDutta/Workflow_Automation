# Multi-Channel Inventory Reconciliation

An end-to-end inventory reconciliation workflow that synchronizes inventory across multiple sales channels, compares channel stock against a centralized master inventory, detects discrepancies, maintains a complete audit trail in PostgreSQL, sends Slack alerts for critical mismatches, and provides a real-time dashboard for inventory visibility and operational monitoring. Built with n8n, PostgreSQL, APIs, Slack, and HTML.

---

## Features

- Automated inventory synchronization
- Multi-channel inventory monitoring
- Shopify, Amazon, eBay, Etsy, and TikTok integration
- Master inventory synchronization
- Inventory reconciliation engine
- Discrepancy detection
- PostgreSQL audit logging
- Slack notifications
- Real-time HTML dashboard
- Inventory drift monitoring
- Scheduled reconciliation every 30 minutes

---

## Tech Stack

- n8n
- PostgreSQL
- Shopify API
- Amazon SP-API
- eBay Inventory API
- Etsy API
- TikTok Shop API
- Slack
- HTML
- JavaScript

---

## Workflow

```

Schedule Trigger (30 min)
│
▼
Fetch Master Inventory
│
▼
Update Master Database
│
▼
Fetch Inventory
├── Shopify
├── Amazon
├── eBay
├── Etsy
└── TikTok
│
▼
Normalize Inventory Data
│
▼
Store Inventory Snapshots
│
▼
Compare Against Master Inventory
│
▼
Determine Inventory Status
│
├───────────────┐
│ │
▼ ▼
Audit Log Slack Alert
│
└───────────────┐
│
▼
Dashboard API
│
▼
HTML Dashboard
