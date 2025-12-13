# Space & Asset Lookup — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 20 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to space and asset documentation
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Identify Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Floor Plans** | Building layouts, space drawings | `https://[tenant].sharepoint.com/...` |
| **Room Inventory** | Room details, capacities, features | `https://[tenant].sharepoint.com/...` |
| **Asset Register** | Equipment list, locations, details | `https://[tenant].sharepoint.com/...` |
| **Building Info** | General building documentation | `https://[tenant].sharepoint.com/...` |

---

## Step 2: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/Facilities/FloorPlans" },
    { "url": "https://contoso.sharepoint.com/sites/Facilities/RoomInventory" },
    { "url": "https://contoso.sharepoint.com/sites/Facilities/AssetRegister" }
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
| "What's the capacity of [room]?" | Returns room details |
| "Where is [equipment] located?" | Returns location |
| "Show me the floor plan for [floor]" | Returns floor plan info |
| "Which rooms have video conferencing?" | Returns filtered list |

---

## Step 5: Roll Out

**Key messages:**
- Agent retrieves info — doesn't book rooms or move assets
- Keep documentation current for best results

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Room not found | Check room inventory is current |
| Outdated floor plan | Update documents when layouts change |
| Asset location wrong | Verify asset register is maintained |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
