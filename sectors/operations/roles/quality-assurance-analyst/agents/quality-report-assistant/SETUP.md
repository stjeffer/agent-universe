# Quality Report Assistant — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 30 minutes |
| **Complexity** | Medium |
| **Capabilities used** | OneDriveAndSharePoint, CodeInterpreter |
| **Actions/Plugins** | None (drafting only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to quality data
- [ ] Quality metrics in Excel or CSV format
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Prepare Your Data

### Data Format Requirements

For best results, ensure your quality data:
- Is in Excel (.xlsx) or CSV format
- Has clear column headers
- Includes date columns
- Uses consistent naming conventions

**Example NCR Log structure:**
```
| NCR # | Date | Category | Description | Disposition | Status | Days Open |
|-------|------|----------|-------------|-------------|--------|-----------|
| NCR-2025-001 | 2025-01-03 | Dimensional | Out of spec | Rework | Closed | 5 |
```

**Example CAPA Tracker:**
```
| CAPA # | Issue | Source | Due Date | Owner | Status | % Complete |
|--------|-------|--------|----------|-------|--------|------------|
| CAPA-2025-001 | Training | NCR | 2025-02-15 | Tom B. | Open | 40 |
```

---

## Step 2: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Quality Metrics** | KPI data exports | `https://[tenant].sharepoint.com/...` |
| **NCR Log** | Non-conformance records | `https://[tenant].sharepoint.com/...` |
| **CAPA Tracker** | Corrective action status | `https://[tenant].sharepoint.com/...` |
| **Report Templates** | Standard report formats | `https://[tenant].sharepoint.com/...` |

---

## Step 3: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        { "url": "https://contoso.sharepoint.com/sites/Quality/Metrics" },
        { "url": "https://contoso.sharepoint.com/sites/Quality/NCRs" },
        { "url": "https://contoso.sharepoint.com/sites/Quality/CAPAs" }
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
| "Help me create the monthly quality report" | Generates structured report draft |
| "Summarize NCRs for [period]" | Returns NCR summary with categories |
| "What's the status of open CAPAs?" | Returns CAPA status table |
| "Analyze quality trends" | Performs trend analysis |

---

## Step 6: Roll Out

**Key messages for users:**
- Agent drafts reports — human review required before distribution
- Quality of output depends on data freshness
- Cannot close CAPAs or approve quality decisions

**Data maintenance:**
- Export quality metrics weekly (or automate)
- Keep NCR and CAPA logs current
- Maintain consistent data formats

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Reports missing recent data | Refresh data exports |
| NCR counts don't match | Verify all NCRs in log |
| CAPA status incorrect | Sync with QMS |
| Charts not generating | Confirm CodeInterpreter enabled |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
