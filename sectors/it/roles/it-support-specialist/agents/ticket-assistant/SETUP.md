# IT Ticket Assistant — Setup Guide

## Overview

This guide walks you through deploying the IT Ticket Assistant agent in your Microsoft 365 environment. Estimated time: **45 minutes**.

---

## Prerequisites

Before starting, ensure you have:

- [ ] **Microsoft 365 Copilot license** assigned to target users
- [ ] **SharePoint sites** with IT templates and policies
- [ ] **Admin access** to Microsoft 365 Admin Center or Teams Admin Center
- [ ] **Copilot Studio access** (for declarative agent deployment)

---

## Step 1: Prepare Your SharePoint Content

The agent references templates and policies to ensure consistent, accurate outputs.

### Recommended Structure

Create or identify SharePoint sites/libraries for:

```
IT-Templates/
├── Ticket-Notes/
│   ├── Resolution-Note-Template.docx
│   └── Escalation-Summary-Template.docx
├── User-Communications/
│   ├── Issue-Resolved-Email-Template.docx
│   ├── Escalation-Notification-Template.docx
│   └── Maintenance-Notice-Template.docx
├── KB-Articles/
│   └── KB-Article-Template.docx
└── Reports/
    └── Weekly-Summary-Template.docx

IT-Policies/
├── Communication-Guidelines.docx
├── Escalation-Procedures.docx
├── SLA-Definitions.docx
└── User-Support-Standards.docx
```

### Template Best Practices

1. **Include placeholders**: Use [BRACKETS] for fields the agent should fill
2. **Add tone guidance**: Include notes on voice and style
3. **Keep templates current**: Update when policies change
4. **Version control**: Use SharePoint versioning to track changes

### Minimum Content for Launch

- [ ] Basic resolution note format/structure
- [ ] User email communication guidelines
- [ ] Escalation requirements and format
- [ ] Ticket categorization guidelines

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
          "url": "https://contoso.sharepoint.com/sites/IT-Templates"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/IT-Policies"
        }
      ]
    },
    {
      "name": "CodeInterpreter"
    }
  ]
}
```

3. **Customize conversation starters** (optional):
   - Adjust language to match your team's terminology
   - Add prompts for common documentation needs

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

---

## Step 4: Configure Permissions

### SharePoint Access

Ensure IT support staff have appropriate access:
- **Read access** to templates and policies
- Consider a security group like "IT-Support-Team"

### CodeInterpreter Note

The CodeInterpreter capability allows the agent to analyze uploaded files (like ticket export CSVs). This:
- Runs in a sandboxed environment
- Does not persist data between sessions
- Only processes files explicitly shared with the agent

---

## Step 5: Test the Agent

### Test Scenarios

| Test | Query | Expected Output |
|------|-------|-----------------|
| Ticket notes | "Write ticket notes for: user couldn't login, password expired, I reset it" | Formatted resolution notes |
| User email | "Write an email explaining we fixed their printer issue" | Professional email draft |
| Escalation | "Create escalation summary: laptop won't boot, tried safe mode, repair" | Structured escalation document |
| KB article | "Draft KB article for fixing Teams camera privacy settings issue" | Formatted KB article |
| Data analysis | Upload CSV + "Summarize last week's tickets" | Summary with metrics |

### What to Check

- [ ] Outputs follow your organizational style
- [ ] Templates and policies are referenced appropriately
- [ ] Tone is professional and empathetic
- [ ] All necessary fields are included
- [ ] CSV analysis works (test with sample data)

---

## Step 6: Roll Out to Users

### Communicate the Launch

Send an announcement to IT support staff:

> **New Tool: IT Ticket Assistant**
>
> We've deployed a new Copilot agent to help you document tickets faster. Instead of writing notes and emails from scratch, use the IT Ticket Assistant:
>
> - "Write ticket notes for [describe issue and fix]"
> - "Compose an email to the user about [resolution]"
> - "Create an escalation summary for Tier 2"
>
> The agent creates drafts for you to review and customize. Give it a try and share feedback!

### Usage Tips for the Team

1. **Be specific**: More details = better output
2. **Review before sending**: Always verify accuracy
3. **Provide feedback**: Tell the agent if something needs adjusting
4. **Use for consistency**: Helps maintain professional standards

---

## Maintenance

### Ongoing Tasks

| Task | Frequency | Owner |
|------|-----------|-------|
| Update templates when processes change | As needed | IT Manager |
| Review agent output quality | Monthly | Team Lead |
| Add new templates for common needs | Quarterly | KB Admin |
| Train new staff on agent usage | Onboarding | Trainer |

### Improving Outputs

If outputs don't match expectations:

1. **Update templates**: Add more detailed examples
2. **Add guidelines**: Document tone and style preferences
3. **Provide more context**: Include relevant policies in SharePoint
4. **Give feedback**: Tell the agent what to adjust

---

## Troubleshooting

| Issue | Likely Cause | Solution |
|-------|--------------|----------|
| Generic outputs | Missing templates/guidelines | Add templates to SharePoint |
| Wrong tone | No communication guidelines | Add tone guidelines document |
| CSV analysis fails | File format issue | Ensure CSV has headers, no special characters |
| Can't find policies | Wrong SharePoint URL | Verify URLs in manifest |
| Slow responses | Large files being analyzed | Use smaller data exports |

---

## Integration Ideas

### With Knowledge Finder

Deploy both agents for a complete solution:
1. **Knowledge Finder** helps locate the solution
2. **Ticket Assistant** helps document it

### With ITSM Systems

While the agent can't directly integrate with ServiceNow/Jira, you can:
- Export ticket data to CSV for analysis
- Copy generated notes into your ticketing system
- Use generated KB articles in your ITSM knowledge base

---

## Support

For issues with this agent:
- **Internal**: Contact your Microsoft 365 admin
- **Microsoft**: [Copilot documentation](https://learn.microsoft.com/en-us/microsoft-365-copilot/)
- **Agent Universe**: [GitHub repository] for updates and community support
