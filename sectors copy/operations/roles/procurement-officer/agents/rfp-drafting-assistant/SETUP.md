# RFP/RFQ Drafting Assistant — Setup Guide

## Overview

This guide walks you through deploying the **RFP/RFQ Drafting Assistant** agent to a Microsoft 365 tenant.

| | |
|---|---|
| **Estimated time** | 25 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (drafting assistance only) |

## Prerequisites

Before you begin, ensure you have:

- [ ] Microsoft 365 Copilot license (for users who will use the agent)
- [ ] Access to SharePoint sites containing procurement templates and documents
- [ ] VS Code with Microsoft 365 Agents Toolkit extension (for pro-code deployment)
  - OR access to Copilot Studio (for low-code deployment)
- [ ] Permissions to deploy apps/agents to your tenant (or admin approval process)

---

## Step 1: Identify Your Knowledge Sources

This agent needs access to SharePoint locations containing RFP/RFQ resources. Identify the URLs for each of the following:

### Required Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **RFP/RFQ Templates** | Approved solicitation templates | `https://[tenant].sharepoint.com/sites/...` |
| **Procurement Policies** | Policy manual, procedures, guidelines | `https://[tenant].sharepoint.com/sites/...` |

### Highly Recommended Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Past Solicitations** | Completed RFPs/RFQs for reference | `https://[tenant].sharepoint.com/sites/...` |
| **Standard Terms & Conditions** | Legal boilerplate, required clauses | `https://[tenant].sharepoint.com/sites/...` |
| **Evaluation Criteria Templates** | Scoring rubrics, criteria frameworks | `https://[tenant].sharepoint.com/sites/...` |
| **Specification Templates** | Technical/functional spec templates | `https://[tenant].sharepoint.com/sites/...` |

### Tips for Identifying Sources

- Check with your procurement team for the "official" template library
- Look for SharePoint sites named: "Procurement", "Templates", "Sourcing", "RFP Library"
- Ensure templates are current — outdated templates can cause compliance issues
- Consider whether past RFPs contain sensitive information (pricing, vendor details) that should be excluded

### Content Organization Recommendations

For best results, your SharePoint content should be organized so the agent can distinguish between:
- **Templates** (blank/starter documents)
- **Past RFPs** (completed solicitations for reference)
- **Policies** (requirements and guidelines)
- **Terms & Conditions** (legal language)

If these are mixed together, consider organizing into subfolders before configuring the agent.

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
    { "url": "https://contoso.sharepoint.com/sites/Procurement/Templates" },
    { "url": "https://contoso.sharepoint.com/sites/Procurement/Policies" },
    { "url": "https://contoso.sharepoint.com/sites/Procurement/Past-RFPs" },
    { "url": "https://contoso.sharepoint.com/sites/Legal/Standard-Terms" }
  ]
}
```

**Important**: 
- Use the actual URLs from Step 1
- More specific URLs (folders) = more focused, relevant results
- Users will only see content they have permission to access

### 2.3 Update the instructions

The `instructions` field in the manifest should contain the full text from `instructions.md`. 

You can either:
- Copy/paste the content from `instructions.md` into the `instructions` field (escape special characters)
- Use a build script to inject it automatically

### 2.4 Customize (optional)

You may optionally customize:
- `name`: Change the display name (keep under 100 characters)
- `description`: Adjust the description for your organization
- `conversation_starters`: Modify prompts to match your terminology (e.g., if you call them "Bid Documents" instead of "RFPs")

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

1. **`id`**: Generate a new GUID
2. **`name.short`**: Display name (e.g., "RFP Assistant")
3. **`name.full`**: Full name (e.g., "RFP/RFQ Drafting Assistant")
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
3. Sign in with your Microsoft 365 account
4. In the Agents Toolkit panel, select **Provision** under Lifecycle
5. Wait for provisioning to complete
6. Select **Publish** to make the agent available

### Option B: Deploy with Copilot Studio

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com/)
2. Create a new agent
3. Configure settings to match the blueprint
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
3. Find and select **RFP/RFQ Drafting Assistant** (or your custom name)

### 5.2 Test with conversation starters

Try each of the pre-configured conversation starters:

| Starter | What to test |
|---------|--------------|
| "Help me draft an RFP for [category]" | Test template retrieval and drafting guidance |
| "What RFP templates do we have for [category]?" | Test template discovery |
| "Help me write specifications for [product]" | Test specification drafting |
| "What evaluation criteria should I use?" | Test criteria framework retrieval |
| "Show me how we handled [X] in past RFPs" | Test past RFP search |
| "What policy language must be included?" | Test policy retrieval |

### 5.3 Verify behavior

- [ ] Agent finds and references templates correctly
- [ ] Agent cites sources (template names, policy sections)
- [ ] Agent marks content as draft / requiring review
- [ ] Agent flags areas needing user input
- [ ] Agent stays in scope (doesn't recommend vendors, set budgets)
- [ ] Agent recommends legal review for complex solicitations

---

## Step 6: Roll Out to Users

### 6.1 Set expectations

Communicate to users:
- This agent produces **drafts** that require human review
- All content should be verified against current policies
- Legal review still required for complex solicitations
- Agent helps with structure and consistency, not final decisions

### 6.2 Training recommendations

Brief training or documentation for users should cover:
- How to access the agent
- What types of requests work well
- How to iterate on drafts (ask follow-up questions)
- When to involve legal or management

### 6.3 Gather feedback

After initial deployment:
- Collect feedback on draft quality
- Note missing templates or policies
- Identify common requests that don't work well
- Track time savings if possible

---

## Troubleshooting

| Issue | Possible Cause | Solution |
|-------|---------------|----------|
| Agent not finding templates | SharePoint URLs incorrect or user lacks access | Verify URLs; check user permissions |
| Outdated template content | Agent using old versions | Ensure SharePoint contains current templates; check versioning |
| Policy references incorrect | Policy documents not in scope or outdated | Add policy folder to capabilities; update policy docs |
| Generic/unhelpful drafts | Not enough past RFPs to learn from | Add more past solicitations to knowledge base |
| RAI validation failure | Instructions contain prohibited content | Review instructions; see [RAI guidelines](https://learn.microsoft.com/en-us/microsoft-365-copilot/extensibility/rai-validation) |

---

## Optional Enhancements

### Enable Web Search for Market Research

To allow the agent to research industry benchmarks or vendor information:

1. Add the `WebSearch` capability to your manifest:

```json
{
  "name": "WebSearch",
  "sites": [
    { "url": "https://www.gartner.com" },
    { "url": "https://www.forrester.com" }
  ]
}
```

2. Update instructions to mention web research capability
3. Consider scoping to trusted industry sites only

### Category-Specific Versions

For organizations with diverse procurement needs, consider creating category-specific variants:
- IT/Software RFP Assistant (scoped to IT templates and policies)
- Construction RFP Assistant (scoped to construction templates)
- Professional Services RFP Assistant

Each variant would have the same structure but different SharePoint sources and potentially customized instructions.

---

## Support

- **Blueprint issues**: Open an issue in the Agent Universe repository
- **Deployment issues**: Contact your Microsoft 365 administrator
- **Copilot issues**: See [Microsoft 365 Copilot documentation](https://learn.microsoft.com/en-us/microsoft-365-copilot/)
