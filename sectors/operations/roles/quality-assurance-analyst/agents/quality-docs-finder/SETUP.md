# Quality Docs Finder — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 25 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to quality documentation
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **SOPs** | Standard Operating Procedures | `https://[tenant].sharepoint.com/...` |
| **Specifications** | Product/material specs | `https://[tenant].sharepoint.com/...` |
| **Standards** | Quality standards docs | `https://[tenant].sharepoint.com/...` |
| **Supplier Quality** | Supplier records, certs | `https://[tenant].sharepoint.com/...` |
| **Calibration** | Calibration records/schedules | `https://[tenant].sharepoint.com/...` |
| **Audit Docs** | Audit reports, findings | `https://[tenant].sharepoint.com/...` |

---

## Step 2: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/Quality/SOPs" },
    { "url": "https://contoso.sharepoint.com/sites/Quality/Specifications" },
    { "url": "https://contoso.sharepoint.com/sites/Quality/SupplierQuality" },
    { "url": "https://contoso.sharepoint.com/sites/Quality/Calibration" },
    { "url": "https://contoso.sharepoint.com/sites/Quality/Audits" }
  ]
}
```

---

## Step 3: Deploy

### Option A: M365 Agents Toolkit
Open in VS Code → Sign in → Provision → Publish

### Option B: Copilot Studio
Create agent → Add SharePoint sources → Add instructions → Publish

---

## Step 4: Test

| Test | Expected Result |
|------|-----------------|
| "Find the SOP for [process]" | Returns SOP with revision info |
| "What's the spec for [part]?" | Returns specification details |
| "Find supplier records for [name]" | Returns supplier quality info |
| "When is [equipment] due for cal?" | Returns calibration status |

---

## Step 5: Roll Out

**Key messages for users:**
- Agent retrieves documents — doesn't modify or approve
- Always verify document revision is current
- Follow document control process for changes

**Document organization tips:**
- Use consistent naming conventions
- Include revision numbers in filenames
- Keep obsolete documents archived separately

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Old revision returned | Check document control; archive obsolete versions |
| Document not found | Verify folder is in scope; check naming |
| Supplier info missing | Ensure supplier folder is included |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
