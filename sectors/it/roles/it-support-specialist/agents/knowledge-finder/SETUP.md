# IT Knowledge Finder — Setup Guide

## Overview

This guide walks you through deploying the IT Knowledge Finder agent in your Microsoft 365 environment. Estimated time: **30 minutes**.

---

## Prerequisites

Before starting, ensure you have:

- [ ] **Microsoft 365 Copilot license** assigned to target users
- [ ] **SharePoint sites** with IT knowledge base content
- [ ] **Admin access** to Microsoft 365 Admin Center or Teams Admin Center
- [ ] **Copilot Studio access** (for declarative agent deployment)

---

## Step 1: Prepare Your SharePoint Content

The agent searches SharePoint for answers. Better organized content = better results.

### Recommended Structure

Create or identify SharePoint sites/libraries for:

```
IT-KnowledgeBase/
├── Articles/
│   ├── Hardware/
│   ├── Software/
│   ├── Network/
│   ├── Security/
│   └── Microsoft 365/
├── FAQs/
└── Error-Codes/

IT-Runbooks/
├── Onboarding/
├── Offboarding/
├── Password-Management/
├── VPN-Configuration/
└── Software-Deployment/

IT-Documentation/
├── Network-Diagrams/
├── Server-Documentation/
├── Configuration-Guides/
└── Vendor-Resources/
```

### Content Best Practices

1. **Use descriptive titles**: "Outlook Error 0x80070005 Resolution" not "KB-234"
2. **Include keywords**: Add error codes, symptoms, and product names
3. **Add metadata**: Tag documents with categories, products, and issue types
4. **Keep content current**: Archive outdated articles, update procedures after changes

### Minimum Content for Launch

To get value from day one, ensure you have:

- [ ] 20+ KB articles covering common issues
- [ ] Password reset procedure
- [ ] VPN setup guide
- [ ] New user onboarding checklist
- [ ] Key system documentation (IP addresses, server names)

---

## Step 2: Configure the Manifest

1. **Copy the manifest template** from `manifest-template.json`

2. **Update SharePoint URLs** with your actual tenant and site URLs:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        {
          "url": "https://contoso.sharepoint.com/sites/IT-KnowledgeBase"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/IT-Documentation"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/IT-Runbooks"
        }
      ]
    }
  ]
}
```

3. **Customize conversation starters** (optional):
   - Update example prompts to match your organization's terminology
   - Add department-specific queries if relevant

---

## Step 3: Deploy the Agent

### Option A: Copilot Studio (Recommended)

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com)
2. Select **Create** → **New agent** → **Configure declarative agent**
3. Upload or paste the manifest JSON
4. Review the configuration and click **Publish**
5. Choose deployment scope (specific users, groups, or organization)

### Option B: Teams Admin Center

1. Go to [Teams Admin Center](https://admin.teams.microsoft.com)
2. Navigate to **Copilot** → **Declarative agents**
3. Click **+ Add** and upload the manifest
4. Configure permissions and publish

### Option C: Developer Deployment

1. Package the manifest as a Teams app (manifest.json in app package)
2. Upload via Teams Admin Center → **Manage apps** → **Upload**
3. Approve and deploy to target users

---

## Step 4: Configure Permissions

Ensure users can access the SharePoint content:

1. **SharePoint Site Permissions**:
   - IT support staff should have at least **Read** access
   - Consider a security group like "IT-Support-Team"

2. **Sensitivity Labels** (if used):
   - Ensure IT knowledge base content doesn't have overly restrictive labels
   - Agent can only access content the user has permission to view

3. **External Sharing**:
   - Disable external sharing on sensitive documentation sites
   - Agent respects SharePoint sharing settings

---

## Step 5: Test the Agent

Before rolling out broadly, test with a small group:

### Test Queries

| Query | Expected Result |
|-------|-----------------|
| "How do I reset a user's password?" | Returns password reset procedure |
| "Error 0x80070005 Office installation" | Returns relevant KB article |
| "What's the IP for DC01?" | Returns network documentation |
| "VPN setup Mac" | Returns macOS VPN procedure |
| "Outlook crashes Finance department" | Returns past ticket resolutions if documented |

### What to Check

- [ ] Agent returns relevant results (not random documents)
- [ ] Source documents are cited correctly
- [ ] Sensitive content is not exposed inappropriately
- [ ] Response time is acceptable (<10 seconds typical)

---

## Step 6: Roll Out to Users

### Communicate the Launch

Send an announcement to IT support staff:

> **New Tool: IT Knowledge Finder**
>
> We've deployed a new Copilot agent to help you find solutions faster. Instead of searching through SharePoint manually, ask the IT Knowledge Finder:
>
> - "Find the fix for [error code]"
> - "What's the procedure for [task]?"
> - "Have we seen issues with [application] before?"
>
> Access it in Microsoft Copilot or Teams. Try it out and share feedback!

### Training Tips

- Demo the agent in a team meeting
- Share example queries that work well
- Encourage staff to report missing documentation (helps improve KB)

---

## Maintenance

### Ongoing Tasks

| Task | Frequency | Owner |
|------|-----------|-------|
| Review agent usage analytics | Monthly | IT Manager |
| Update KB with new solutions | Weekly | Support Team |
| Archive outdated content | Quarterly | KB Admin |
| Refresh SharePoint URLs if sites change | As needed | Admin |

### Improving Results

If the agent returns poor results:

1. **Check content quality**: Is the information in SharePoint?
2. **Improve titles/keywords**: Make content more searchable
3. **Add metadata**: Tag documents with relevant terms
4. **Create missing articles**: If common questions have no KB article, create one

---

## Troubleshooting

| Issue | Likely Cause | Solution |
|-------|--------------|----------|
| Agent returns no results | Content not in SharePoint or wrong URL | Verify SharePoint URLs in manifest |
| Agent returns wrong documents | Poor document titles/keywords | Improve content metadata |
| Users can't access agent | Permissions not configured | Check Copilot license and deployment scope |
| Slow responses | Large SharePoint sites | Consider narrowing scope to specific libraries |
| Sensitive data exposed | Permissions too broad | Review SharePoint site permissions |

---

## Support

For issues with this agent:
- **Internal**: Contact your Microsoft 365 admin
- **Microsoft**: [Copilot documentation](https://learn.microsoft.com/en-us/microsoft-365-copilot/)
- **Agent Universe**: [GitHub repository] for updates and community support
