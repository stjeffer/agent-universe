# Contract & Supplier Finder — Setup Guide

## Overview

This guide walks you through deploying the **Contract & Supplier Finder** agent to a Microsoft 365 tenant.

| | |
|---|---|
| **Estimated time** | 20 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

Before you begin, ensure you have:

- [ ] Microsoft 365 Copilot license (for users who will use the agent)
- [ ] Access to SharePoint sites containing procurement documentation
- [ ] VS Code with Microsoft 365 Agents Toolkit extension (for pro-code deployment)
  - OR access to Copilot Studio (for low-code deployment)
- [ ] Permissions to deploy apps/agents to your tenant (or admin approval process)

---

## Step 1: Identify Your Knowledge Sources

This agent needs access to SharePoint locations containing procurement documentation. Identify the URLs for each of the following:

### Required Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Active Contracts** | Currently effective contracts and agreements | `https://[tenant].sharepoint.com/sites/...` |
| **Supplier/Vendor Files** | Vendor profiles, onboarding docs, contact info | `https://[tenant].sharepoint.com/sites/...` |

### Recommended Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Archived Contracts** | Expired or historical contracts | `https://[tenant].sharepoint.com/sites/...` |
| **RFP/RFQ Responses** | Vendor responses to solicitations | `https://[tenant].sharepoint.com/sites/...` |
| **Performance Evaluations** | Supplier scorecards and reviews | `https://[tenant].sharepoint.com/sites/...` |
| **Pricing/Quote History** | Historical pricing documents | `https://[tenant].sharepoint.com/sites/...` |

### Tips for Identifying Sources

- Check with your procurement team lead for the "official" contract repository
- Look for SharePoint sites named like: "Procurement", "Contracts", "Vendor Management", "Sourcing"
- Consider whether archived/historical data should be included
- Note any folders that contain sensitive contracts that should be excluded

---

## Step 2: Prepare the Manifest

### 2.1 Copy the template

Copy `manifest-template.json` and rename it to `declarativeAgent.json`.

### 2.2 Update SharePoint URLs

Find the `capabilities` section and replace the placeholder URLs with your actual SharePoint locations:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/Procurement/Contracts" },
    { "url": "https://contoso.sharepoint.com/sites/Procurement/Vendors" },
    { "url": "https://contoso.sharepoint.com/sites/Procurement/RFP-Responses" }
  ]
}
```

**Important**: 
- Use the actual URLs from Step 1
- You can include multiple URLs (folders or sites)
- Users will only see content they have permission to access
- More specific URLs (folders) = more focused results

### 2.3 Update the instructions

The `instructions` field in the manifest should contain the full text from `instructions.md`. 

You can either:
- Copy/paste the content from `instructions.md` into the `instructions` field (escape any special characters)
- Or use a build script to inject it automatically

### 2.4 Customize (optional)

You may optionally customize:
- `name`: Change the display name (keep under 100 characters)
- `description`: Adjust the description for your organization
- `conversation_starters`: Modify the example prompts to match your terminology

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

Open `manifest.json` and update:

1. **`id`**: Generate a new GUID (use https://www.guidgenerator.com/ or `uuidgen` in terminal)
2. **`name.short`**: Display name (e.g., "Contract Finder")
3. **`name.full`**: Full name (e.g., "Contract & Supplier Finder")
4. **`description.short`**: Brief description
5. **`description.full`**: Detailed description

### 3.2 Add icons

Replace the placeholder icons with your organization's branded versions, or use the defaults:
- `color.png`: 192x192 pixels, full color
- `outline.png`: 32x32 pixels, single color outline

---

## Step 4: Deploy the Agent

### Option A: Deploy with Microsoft 365 Agents Toolkit (Recommended)

1. Open the agent folder in VS Code
2. Ensure the **Microsoft 365 Agents Toolkit** extension is installed
3. Sign in with your Microsoft 365 account (must have appropriate permissions)
4. In the Agents Toolkit panel, select **Provision** under Lifecycle
5. Wait for provisioning to complete
6. Select **Publish** to make the agent available

### Option B: Deploy with Copilot Studio

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com/)
2. Create a new agent
3. Configure the agent settings to match the blueprint
4. Add the SharePoint knowledge sources
5. Copy the instructions from `instructions.md`
6. Add the conversation starters
7. Publish the agent

### Option C: Manual Upload (Admin)

1. Zip the contents of the `appPackage` folder
2. Go to [Microsoft 365 Admin Center](https://admin.microsoft.com)
3. Navigate to **Settings** > **Integrated Apps**
4. Select **Upload custom apps**
5. Upload the zip file
6. Approve and deploy to users

---

## Step 5: Test the Agent

### 5.1 Access the agent

1. Open Microsoft 365 Copilot at https://m365.cloud.microsoft/chat
2. Click the conversation drawer icon (next to "New Chat")
3. Find and select **Contract & Supplier Finder** (or your custom name)

### 5.2 Test with conversation starters

Try each of the pre-configured conversation starters:

| Starter | What to test |
|---------|--------------|
| "Find our current contract with [supplier]" | Use a real supplier name from your contracts |
| "What do we have on file for [supplier]?" | Test supplier information retrieval |
| "What pricing have we had with [supplier]?" | Test historical data access |
| "Which contracts are expiring in the next 90 days?" | Test date-based queries |

### 5.3 Verify behavior

- [ ] Agent finds documents in the configured SharePoint locations
- [ ] Agent cites sources (document names, locations)
- [ ] Agent stays in scope (doesn't try to create/modify documents)
- [ ] Agent handles missing information gracefully
- [ ] Agent respects user permissions (users only see what they can access)

---

## Step 6: Roll Out to Users

### 6.1 Communicate availability

Notify procurement team members that the agent is available:
- What it does
- How to access it
- Example use cases
- Who to contact for issues

### 6.2 Gather feedback

After initial deployment:
- Collect feedback on usefulness
- Note any missing knowledge sources
- Identify conversation patterns that don't work well
- Track time savings if possible

### 6.3 Iterate

Based on feedback:
- Add additional SharePoint sources if needed
- Refine instructions for edge cases
- Add new conversation starters for common queries

---

## Troubleshooting

| Issue | Possible Cause | Solution |
|-------|---------------|----------|
| Agent not appearing in Copilot | Provisioning incomplete or pending admin approval | Check deployment status; contact IT admin |
| "No results found" for known documents | SharePoint URLs incorrect or user lacks access | Verify URLs; check user permissions |
| Agent returns wrong documents | SharePoint scope too broad | Narrow URLs to specific folders |
| RAI validation failure | Instructions contain prohibited content | Review instructions for harmful language; see [RAI guidelines](https://learn.microsoft.com/en-us/microsoft-365-copilot/extensibility/rai-validation) |
| Slow responses | Too many SharePoint sources configured | Reduce number of sources; use more specific folders |

---

## Optional Enhancements

### Enable Email Search

To allow the agent to search email for supplier correspondence:

1. Add the `Email` capability to your manifest:

```json
{
  "name": "Email"
}
```

2. Update instructions to mention email search capability

### Enable ERP Integration

If your organization has Microsoft Graph connectors for procurement systems:

1. Get the connection ID from your IT admin
2. Add the `GraphConnectors` capability:

```json
{
  "name": "GraphConnectors",
  "connections": [
    { "connection_id": "your-erp-connector-id" }
  ]
}
```

---

## Support

- **Blueprint issues**: Open an issue in the Agent Universe repository
- **Deployment issues**: Contact your Microsoft 365 administrator
- **Copilot issues**: See [Microsoft 365 Copilot documentation](https://learn.microsoft.com/en-us/microsoft-365-copilot/)
