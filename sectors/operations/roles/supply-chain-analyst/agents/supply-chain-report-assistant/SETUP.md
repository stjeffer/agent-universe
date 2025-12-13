# Supply Chain Report Assistant — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 30 minutes |
| **Complexity** | Medium |
| **Capabilities used** | OneDriveAndSharePoint, CodeInterpreter |
| **Actions/Plugins** | None (analysis only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to supply chain data exports
- [ ] Data in analyzable format (Excel, CSV)
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Prepare Your Data

### Data Format Requirements

| Format | Supported | Notes |
|--------|-----------|-------|
| Excel (.xlsx) | ✅ Yes | Preferred |
| CSV | ✅ Yes | Good for large datasets |
| PDF reports | ⚠️ Limited | Tables may not extract cleanly |

### Recommended Data Structure

For best results, include structured data with:
- Clear column headers
- Consistent date formats
- Numeric values (not formatted as text)
- Period identifiers (week, month, quarter)

### Suggested Data Files

| Data Type | Refresh Frequency | Contents |
|-----------|-------------------|----------|
| Inventory metrics | Daily/Weekly | Levels, turns, days of supply |
| Delivery performance | Daily/Weekly | OTIF, fill rate, cycle time |
| Order data | Daily | Orders, shipments, backorders |
| Historical KPIs | Weekly/Monthly | Trend data for comparison |

---

## Step 2: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Data Exports** | Supply chain metrics files | `https://[tenant].sharepoint.com/...` |
| **Report Templates** | Previous report formats | `https://[tenant].sharepoint.com/...` |
| **KPI Definitions** | Target definitions, calculations | `https://[tenant].sharepoint.com/...` |
| **Historical Reports** | Past reports for comparison | `https://[tenant].sharepoint.com/...` |

---

## Step 3: Prepare the Manifest

### 3.1 Copy and configure

Copy `manifest-template.json` to `declarativeAgent.json` and update:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        { "url": "https://contoso.sharepoint.com/sites/SupplyChain/DataExports" },
        { "url": "https://contoso.sharepoint.com/sites/SupplyChain/Reports" },
        { "url": "https://contoso.sharepoint.com/sites/SupplyChain/KPIs" }
      ]
    },
    {
      "name": "CodeInterpreter"
    }
  ]
}
```

### 3.2 Verify CodeInterpreter

CodeInterpreter is essential for calculations and visualizations. Ensure it's in your capabilities.

---

## Step 4: Deploy

### Option A: M365 Agents Toolkit
1. Open in VS Code
2. Sign in to Microsoft 365
3. Provision → Publish

### Option B: Copilot Studio
1. Create new agent
2. Add SharePoint sources
3. Enable Code Interpreter
4. Add instructions and starters
5. Publish

---

## Step 5: Test

| Test | What to verify |
|------|----------------|
| "Create a weekly summary" | Report generation |
| "Analyze inventory turns" | Calculations work |
| "What's our on-time delivery rate?" | KPI retrieval |
| "Show trend over past quarter" | Trend analysis |

Verify:
- [ ] Agent finds and reads data files
- [ ] Calculations are accurate
- [ ] Visualizations generate correctly
- [ ] Sources are cited
- [ ] Caveats noted appropriately

---

## Step 6: Roll Out

### Set expectations
- Reports are **drafts** requiring review
- Data freshness depends on exports
- Verify critical metrics in source systems

### Data maintenance
- Regular data exports to SharePoint
- Consistent file naming
- Archive old data periodically

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't find data | Verify SharePoint URLs |
| Wrong calculations | Check data format (numbers vs text) |
| No visualizations | Ensure CodeInterpreter enabled |
| Outdated analysis | Refresh data exports |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
