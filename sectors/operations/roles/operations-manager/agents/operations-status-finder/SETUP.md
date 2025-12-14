# Operations Status Finder — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 25 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to operational documentation
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Project Status** | Project reports, updates, trackers | `https://[tenant].sharepoint.com/...` |
| **Team Updates** | Meeting notes, team reports | `https://[tenant].sharepoint.com/...` |
| **Departmental Reports** | Weekly/monthly department summaries | `https://[tenant].sharepoint.com/...` |
| **Operational Dashboards** | KPI documents, performance summaries | `https://[tenant].sharepoint.com/...` |

---

## Step 2: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/Operations/Projects" },
    { "url": "https://contoso.sharepoint.com/sites/Operations/TeamUpdates" },
    { "url": "https://contoso.sharepoint.com/sites/Operations/Reports" }
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
| "What's the status of [project]?" | Returns project status and details |
| "What are the latest updates from [team]?" | Returns recent team updates |
| "Summarize operational updates this week" | Returns cross-departmental summary |
| "Are there any open issues?" | Returns blockers and escalations |

---

## Step 5: Roll Out

**Key messages for users:**
- Agent retrieves status info — doesn't update statuses
- Best results when status reports are kept current
- Verify critical information with project owners

**Success factors:**
- Teams maintain regular status update cadence
- Consistent document naming and structure
- Recent documents available in SharePoint

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Status info outdated | Encourage teams to update reports regularly |
| Can't find project | Check project docs are in scope |
| Missing department info | Add department SharePoint sites to scope |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
