# Operations Report Assistant — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 30 minutes |
| **Complexity** | Medium |
| **Capabilities used** | OneDriveAndSharePoint, CodeInterpreter |
| **Actions/Plugins** | None (drafting only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to operational data
- [ ] KPI data in Excel or CSV format
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Prepare Your Data

### Data Format Requirements

For best results, ensure your KPI data:
- Is in Excel (.xlsx) or CSV format
- Has clear column headers
- Includes date/period columns
- Uses consistent naming conventions
- Is refreshed regularly (weekly recommended)

**Example structure:**
```
| Date | Department | KPI | Actual | Target | Prior Period |
|------|------------|-----|--------|--------|--------------|
| 2025-01-10 | Production | Output | 12450 | 11850 | 11525 |
```

---

## Step 2: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **KPI Data** | Performance data exports | `https://[tenant].sharepoint.com/...` |
| **Historical Reports** | Past reports for reference | `https://[tenant].sharepoint.com/...` |
| **Templates** | Report templates | `https://[tenant].sharepoint.com/...` |
| **Meeting Materials** | Agendas, presentations | `https://[tenant].sharepoint.com/...` |

---

## Step 3: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        { "url": "https://contoso.sharepoint.com/sites/Operations/KPIData" },
        { "url": "https://contoso.sharepoint.com/sites/Operations/Reports" }
      ]
    },
    {
      "name": "CodeInterpreter"
    }
  ]
}
```

---

## Step 4: Deploy

### Option A: M365 Agents Toolkit
Open in VS Code → Sign in → Provision → Publish

### Option B: Copilot Studio
Create agent → Add SharePoint sources → Enable CodeInterpreter → Add instructions → Publish

---

## Step 5: Test

| Test | Expected Result |
|------|-----------------|
| "Help me create the weekly operations report" | Generates structured report draft |
| "Summarize our KPIs for [period]" | Returns KPI summary with comparisons |
| "Draft an executive summary" | Creates concise leadership update |
| "Analyze trends over past quarter" | Performs trend analysis |

---

## Step 6: Roll Out

**Key messages for users:**
- Agent drafts reports — human review required before distribution
- Quality of output depends on data freshness
- CodeInterpreter enables calculations and visualizations

**Data maintenance:**
- Export KPI data weekly (or automate)
- Keep historical reports for comparison
- Maintain consistent data formats

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Reports missing recent data | Refresh KPI exports |
| Calculations incorrect | Verify data format and column headers |
| Can't compare periods | Ensure historical data is available |
| Visualizations not working | Confirm CodeInterpreter is enabled |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
