# HR Document Assistant — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 30 minutes |
| **Complexity** | Medium |
| **Capabilities used** | OneDriveAndSharePoint, CodeInterpreter (optional) |
| **Actions/Plugins** | None (drafting only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to HR templates
- [ ] Document templates (offer letters, job descriptions, etc.)
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Gather Your Templates

Collect current versions of:

| Template Type | Example Documents |
|---------------|-------------------|
| **Offer Letters** | Standard offer, executive offer, intern offer |
| **Job Descriptions** | Template + sample JDs by level |
| **Onboarding** | Welcome email, first day checklist |
| **Communications** | Policy announcement, employee update |
| **Reports** | Monthly HR metrics template |

---

## Step 2: Organize in SharePoint

Recommended structure:
```
HR Templates/
├── Offer Letters/
│   ├── Standard_Offer_Template.docx
│   ├── Executive_Offer_Template.docx
│   └── Samples/
├── Job Descriptions/
│   ├── JD_Template.docx
│   └── Library/
├── Onboarding/
│   ├── Welcome_Email_Template.docx
│   └── First_Day_Checklist.docx
├── Communications/
│   └── Policy_Announcement_Template.docx
└── Reports/
    └── Monthly_HR_Metrics_Template.xlsx
```

---

## Step 3: Configure Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Templates** | HR document templates | `https://[tenant].sharepoint.com/...` |
| **Samples** | Example documents | `https://[tenant].sharepoint.com/...` |
| **Style Guide** | Company writing guidelines | `https://[tenant].sharepoint.com/...` |
| **JD Library** | Existing job descriptions | `https://[tenant].sharepoint.com/...` |

---

## Step 4: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        { "url": "https://contoso.sharepoint.com/sites/HR/Templates" },
        { "url": "https://contoso.sharepoint.com/sites/HR/JobDescriptions" }
      ]
    }
  ]
}
```

**For reporting capabilities, add:**
```json
{
  "name": "CodeInterpreter"
}
```

---

## Step 5: Deploy

### Option A: M365 Agents Toolkit
Open in VS Code → Sign in → Provision → Publish

### Option B: Copilot Studio
Create agent → Add SharePoint sources → Add instructions → Publish

---

## Step 6: Test

| Test | Expected Result |
|------|-----------------|
| "Help me draft an offer letter for [position]" | Generates offer letter with placeholders |
| "Create a job description for [role]" | Generates JD following template structure |
| "Draft a welcome email for new hire" | Generates onboarding email |
| "Help me communicate [policy] change" | Generates policy announcement |

---

## Step 7: Roll Out

**Key messages for HR team:**
- Agent drafts documents — always review before use
- Placeholders [IN BRACKETS] need to be filled in
- Follow existing approval processes
- Flag any compliance concerns to legal

**Template maintenance:**
- Update templates as policies change
- Add new samples to improve quality
- Review agent outputs quarterly

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Documents don't match company style | Add more sample documents to training |
| Missing sections | Update templates with all required sections |
| Outdated language | Refresh templates with current policies |
| Wrong format | Specify format requirements in the request |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
