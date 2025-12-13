# Inventory & Order Tracker — Setup Guide

## Overview

This guide walks you through deploying the **Inventory & Order Tracker** agent to a Microsoft 365 tenant.

| | |
|---|---|
| **Estimated time** | 20 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

Before you begin, ensure you have:

- [ ] Microsoft 365 Copilot license (for users who will use the agent)
- [ ] Access to SharePoint sites containing inventory and order documents
- [ ] VS Code with Microsoft 365 Agents Toolkit extension (for pro-code deployment)
  - OR access to Copilot Studio (for low-code deployment)
- [ ] Permissions to deploy apps/agents to your tenant (or admin approval process)

---

## Step 1: Identify Your Knowledge Sources

This agent needs access to supply chain documents. Identify the SharePoint URLs for each:

### Required Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Inventory Reports** | Daily/weekly inventory snapshots, level reports | `https://[tenant].sharepoint.com/sites/...` |
| **Order Tracking** | PO status logs, order documents | `https://[tenant].sharepoint.com/sites/...` |

### Highly Recommended Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Shipment Tracking** | Delivery schedules, carrier tracking docs | `https://[tenant].sharepoint.com/sites/...` |
| **Exception Reports** | Low stock alerts, backorder reports | `https://[tenant].sharepoint.com/sites/...` |
| **Supplier Schedules** | Inbound delivery calendars | `https://[tenant].sharepoint.com/sites/...` |

### Data Freshness Considerations

This agent works with **document-based data**, not live ERP connections. For best results:

- **Export inventory reports daily** from your ERP to SharePoint
- **Update order tracking** as statuses change
- **Timestamp documents** so users know data currency
- Consider **Power Automate flows** to automate exports

---

## Step 2: Prepare the Manifest

### 2.1 Copy the template

Copy `manifest-template.json` and rename it to `declarativeAgent.json`.

### 2.2 Update SharePoint URLs

Find the `capabilities` section and replace placeholder URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/SupplyChain/InventoryReports" },
    { "url": "https://contoso.sharepoint.com/sites/SupplyChain/OrderTracking" },
    { "url": "https://contoso.sharepoint.com/sites/SupplyChain/ShipmentLogs" },
    { "url": "https://contoso.sharepoint.com/sites/SupplyChain/Exceptions" }
  ]
}
```

### 2.3 Update the instructions

Copy the content from `instructions.md` into the `instructions` field of the manifest.

---

## Step 3: Prepare the App Package

Your `appPackage` folder should contain:

```
appPackage/
├── manifest.json           # M365 app manifest
├── declarativeAgent.json   # Declarative agent manifest (from Step 2)
├── color.png              # 192x192 color icon
└── outline.png            # 32x32 outline icon
```

### 3.1 Update manifest.json

1. **`id`**: Generate a new GUID
2. **`name.short`**: Display name (e.g., "Inventory Tracker")
3. **`name.full`**: Full name
4. **`description.short`**: Brief description
5. **`description.full`**: Detailed description

---

## Step 4: Deploy the Agent

### Option A: Deploy with Microsoft 365 Agents Toolkit (Recommended)

1. Open the agent folder in VS Code
2. Sign in with your Microsoft 365 account
3. In the Agents Toolkit panel, select **Provision**
4. Select **Publish** to make available

### Option B: Deploy with Copilot Studio

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com/)
2. Create a new agent
3. Add SharePoint knowledge sources
4. Copy instructions from `instructions.md`
5. Add conversation starters
6. Publish

---

## Step 5: Test the Agent

### 5.1 Access the agent

1. Open Microsoft 365 Copilot
2. Select the agent from the conversation drawer

### 5.2 Test with conversation starters

| Starter | What to test |
|---------|--------------|
| "What's the current inventory level for [SKU]?" | Inventory lookup |
| "Find the status of order [PO number]" | Order tracking |
| "Where is the shipment from [supplier]?" | Shipment tracking |
| "Which items are below safety stock?" | Exception reports |
| "What orders are on backorder?" | Backorder status |
| "What deliveries are expected this week?" | Delivery schedule |

### 5.3 Verify behavior

- [ ] Agent finds inventory data correctly
- [ ] Agent cites document names and dates
- [ ] Agent notes data freshness appropriately
- [ ] Agent stays in scope (retrieval, not recommendations)
- [ ] Agent acknowledges when information isn't found

---

## Step 6: Roll Out to Users

### 6.1 Set expectations

Communicate to users:
- Agent searches **document-based data**, not live ERP
- Data freshness depends on export frequency
- Verify critical decisions in source systems
- Agent retrieves but doesn't modify data

### 6.2 Establish data maintenance

For optimal agent performance:
- Daily inventory report exports
- Timely order status updates
- Clear document naming conventions
- Archive old reports periodically

---

## Troubleshooting

| Issue | Possible Cause | Solution |
|-------|---------------|----------|
| Can't find inventory data | SharePoint URLs incorrect | Verify URLs; check user permissions |
| Data is outdated | Reports not being refreshed | Set up regular exports from ERP |
| SKU not found | Different naming in documents | Check document formats; align naming |
| Slow responses | Too many documents in scope | Narrow SharePoint folders; archive old data |

---

## Optional Enhancements

### Add Graph Connectors for ERP

If your organization has Graph connectors for SAP, Oracle, or other systems:

```json
{
  "name": "GraphConnectors",
  "connections": [
    { "connection_id": "your-erp-connector-id" }
  ]
}
```

This enables more real-time data access.

### Enable Email Search

To search order confirmations and supplier communications:

```json
{
  "name": "Email"
}
```

---

## Support

- **Blueprint issues**: Open an issue in the Agent Universe repository
- **Deployment issues**: Contact your Microsoft 365 administrator
