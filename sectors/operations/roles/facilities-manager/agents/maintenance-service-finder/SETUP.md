# Maintenance & Service Finder — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 20 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to facilities documentation
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Maintenance Records** | Work order history, service logs | `https://[tenant].sharepoint.com/...` |
| **Vendor Contracts** | Service agreements, terms | `https://[tenant].sharepoint.com/...` |
| **Vendor Directory** | Contact info, service areas | `https://[tenant].sharepoint.com/...` |
| **Equipment Docs** | Manuals, specs, warranty info | `https://[tenant].sharepoint.com/...` |
| **Compliance Records** | Inspections, certifications | `https://[tenant].sharepoint.com/...` |

---

## Step 2: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/Facilities/MaintenanceRecords" },
    { "url": "https://contoso.sharepoint.com/sites/Facilities/VendorContracts" },
    { "url": "https://contoso.sharepoint.com/sites/Facilities/EquipmentDocs" },
    { "url": "https://contoso.sharepoint.com/sites/Facilities/Compliance" }
  ]
}
```

---

## Step 3: Deploy

### Option A: M365 Agents Toolkit
1. Open in VS Code → Sign in → Provision → Publish

### Option B: Copilot Studio
1. Create agent → Add SharePoint sources → Add instructions → Publish

---

## Step 4: Test

| Test | Expected Result |
|------|-----------------|
| "What's the maintenance history for [equipment]?" | Shows service history |
| "Who do we call for [service type]?" | Returns vendor contact |
| "Find our contract with [vendor]" | Shows contract details |
| "When was [equipment] last serviced?" | Returns date and details |
| "Find the latest [inspection] report" | Returns inspection results |

---

## Step 5: Roll Out

**Key messages for users:**
- Agent retrieves info — doesn't create work orders
- Verify critical details in source systems
- Keep documents updated for best results

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't find vendor info | Check vendor directory is in scope |
| Outdated maintenance records | Export/refresh from CMMS |
| Contract details missing | Ensure contracts folder included |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
