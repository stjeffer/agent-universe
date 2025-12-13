# Inventory & Order Tracker

A Microsoft 365 Copilot declarative agent that helps supply chain analysts quickly find inventory status, order information, and supply chain exceptions.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Supply Chain Analyst |
| **Complexity** | Low |
| **Setup Time** | ~20 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

This agent provides fast access to supply chain status information:

- **Find inventory levels** for specific SKUs or products
- **Look up order status** and tracking details
- **Track shipments** and delivery schedules
- **Identify exceptions** — items below safety stock, backorders
- **Surface supplier deliveries** expected this week

## What it doesn't do

- Modify inventory levels or orders
- Make ordering recommendations
- Access live ERP data (uses document-based data)
- Perform demand forecasting

## Friction addressed

| Friction Type | Description | Time Saved |
|---------------|-------------|------------|
| Information seeking | Finding inventory and order data across systems | 2 hrs/week |
| Context switching | Moving between multiple systems/documents | 1.5 hrs/week |
| Exception identification | Finding low stock and backorder issues | 0.5 hrs/week |

## Quick start

1. **Identify** SharePoint locations with inventory reports, order logs, shipment tracking
2. **Configure** the manifest with your URLs
3. **Deploy** using M365 Agents Toolkit or Copilot Studio
4. **Test** with conversation starters

See [SETUP.md](SETUP.md) for detailed instructions.

## Files

| File | Purpose |
|------|---------|
| `blueprint.json` | Structured agent definition and metadata |
| `instructions.md` | Human-readable agent instructions |
| `manifest-template.json` | M365 manifest with placeholders |
| `SETUP.md` | Step-by-step deployment guide |

## Example conversations

**Inventory lookup:**
> "What's the current inventory level for SKU-7842?"

**Order status:**
> "Find the status of order PO-2025-0142"

**Exception identification:**
> "Which items are below safety stock right now?"

**Delivery tracking:**
> "What deliveries are expected from GlobalParts this week?"

## Important notes

- Agent searches **document-based data**, not live ERP
- Data freshness depends on export frequency to SharePoint
- For critical decisions, verify in source systems
- Works best with regular, timestamped report exports

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to inventory and order documents
- Regular data exports from ERP/WMS to SharePoint
