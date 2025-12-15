# HR Policy & Benefits Finder — Setup Guide

## Overview

| | |
|---|---|
| **Estimated time** | 20 minutes |
| **Complexity** | Low |
| **Capabilities used** | OneDriveAndSharePoint |
| **Actions/Plugins** | None (retrieval only) |

## Prerequisites

- [ ] Microsoft 365 Copilot license
- [ ] SharePoint access to HR documentation
- [ ] Current employee handbook
- [ ] VS Code with M365 Agents Toolkit OR Copilot Studio access

---

## Step 1: Gather Your HR Documentation

Ensure you have current versions of:

| Document | Location | Last Updated |
|----------|----------|--------------|
| Employee Handbook | `SharePoint URL` | Date |
| Benefits Guide | `SharePoint URL` | Date |
| PTO/Leave Policies | `SharePoint URL` | Date |
| Expense Policy | `SharePoint URL` | Date |
| Remote Work Guidelines | `SharePoint URL` | Date |

**Tip:** Consolidate HR documents in a single SharePoint site for easier configuration.

---

## Step 2: Configure Knowledge Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Employee Handbook** | Full handbook document | `https://[tenant].sharepoint.com/...` |
| **Benefits** | Benefits guides, summaries | `https://[tenant].sharepoint.com/...` |
| **Policies** | HR policies and procedures | `https://[tenant].sharepoint.com/...` |
| **Forms** | HR forms and templates | `https://[tenant].sharepoint.com/...` |

---

## Step 3: Configure the Manifest

Copy `manifest-template.json` to `declarativeAgent.json` and update URLs:

```json
{
  "name": "OneDriveAndSharePoint",
  "items_by_url": [
    { "url": "https://contoso.sharepoint.com/sites/HR/Handbook" },
    { "url": "https://contoso.sharepoint.com/sites/HR/Benefits" },
    { "url": "https://contoso.sharepoint.com/sites/HR/Policies" }
  ]
}
```

---

## Step 4: Deploy

### Option A: M365 Agents Toolkit
Open in VS Code → Sign in → Provision → Publish

### Option B: Copilot Studio
Create agent → Add SharePoint sources → Add instructions → Publish

---

## Step 5: Test

| Test | Expected Result |
|------|-----------------|
| "How much PTO do I get?" | Returns PTO policy with accrual rates |
| "When is open enrollment?" | Returns enrollment dates and process |
| "What's the parental leave policy?" | Returns leave duration and eligibility |
| "How do I submit expenses?" | Returns expense process steps |

---

## Step 6: Deployment Options

### Option A: HR Team Only
Deploy to HR generalists to help them answer employee questions faster.

### Option B: All Employees (Recommended)
Deploy to all employees for self-service, reducing HR inquiry volume.

**If deploying to all employees:**
- Add clear disclaimer about consulting HR for complex situations
- Ensure handbook and benefits info is employee-appropriate
- Consider creating a "HR Help" Teams channel for the agent

---

## Step 7: Roll Out

**Key messages for employees:**
- Agent answers common policy and benefits questions
- For complex situations or exceptions, still contact HR
- Information is based on current policies — always check for updates

**Key messages for HR team:**
- Agent handles routine inquiries
- Escalate complex situations to HR directly
- Keep source documents updated

---

## Maintenance

| Task | Frequency |
|------|-----------|
| Update employee handbook | As policies change |
| Update benefits guides | Annually (before open enrollment) |
| Review agent responses | Quarterly |
| Check for outdated information | Monthly |

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Wrong policy information | Check source document version |
| Can't find benefits info | Verify benefits folder is in scope |
| Outdated dates | Update source documents |
| Too much jargon | Simplify source documents or add glossary |

---

## Support

- Blueprint issues: Agent Universe repository
- Deployment: Microsoft 365 admin
