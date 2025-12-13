# Procurement Spend Analyst — Setup Guide

## Overview

This guide walks you through deploying the **Procurement Spend Analyst** agent to a Microsoft 365 tenant.

| | |
|---|---|
| **Estimated time** | 30 minutes |
| **Complexity** | Medium |
| **Capabilities used** | OneDriveAndSharePoint, CodeInterpreter |
| **Actions/Plugins** | None (analysis only) |

## Prerequisites

Before you begin, ensure you have:

- [ ] Microsoft 365 Copilot license (for users who will use the agent)
- [ ] Access to SharePoint sites containing spend data and reports
- [ ] Spend data in analyzable formats (Excel, CSV — not just PDFs)
- [ ] VS Code with Microsoft 365 Agents Toolkit extension (for pro-code deployment)
  - OR access to Copilot Studio (for low-code deployment)
- [ ] Permissions to deploy apps/agents to your tenant (or admin approval process)

---

## Step 1: Prepare Your Spend Data

This agent works best with structured, analyzable data. Before setup, ensure your data meets these requirements:

### Data Format Requirements

| Format | Supported | Notes |
|--------|-----------|-------|
| Excel (.xlsx) | ✅ Yes | Preferred — preserves structure |
| CSV | ✅ Yes | Good for large datasets |
| PDF reports | ⚠️ Limited | Can extract some data; structured tables work better |
| Images/scans | ❌ No | Not analyzable |

### Recommended Data Structure

For best results, spend data should include columns like:

```
| PO Number | Supplier | Category | Amount | Date | Department | Status |
```

### Data Freshness Considerations

- Agent analyzes data as stored in SharePoint
- For current analysis, upload recent data extracts
- Consider automated exports from your ERP if available
- Document the "as of" date for any data files

---

## Step 2: Identify Your Knowledge Sources

Identify the SharePoint URLs for each data source:

### Required Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Spend Reports** | Periodic spend extracts (Excel/CSV) | `https://[tenant].sharepoint.com/sites/...` |
| **Supplier Performance** | Scorecards, ratings, delivery metrics | `https://[tenant].sharepoint.com/sites/...` |

### Recommended Sources

| Content Type | Description | Your URL |
|--------------|-------------|----------|
| **Contract Summaries** | Contract values for spend context | `https://[tenant].sharepoint.com/sites/...` |
| **Category Definitions** | Spend category taxonomy | `https://[tenant].sharepoint.com/sites/...` |
| **Historical Data** | Prior period data for trend analysis | `https://[tenant].sharepoint.com/sites/...` |
| **Benchmark Data** | Industry benchmarks, targets | `https://[tenant].sharepoint.com/sites/...` |

### Tips for Data Organization

- Keep current period data separate from historical
- Use consistent file naming (e.g., `Spend_Report_2024_Q3.xlsx`)
- Include a data dictionary or column definitions
- Remove sensitive PII if not needed for analysis

---

## Step 3: Prepare the Manifest

### 3.1 Copy the template

Copy `manifest-template.json` and rename it to `declarativeAgent.json`.

### 3.2 Update SharePoint URLs

Find the `capabilities` section and replace the placeholder URLs:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        { "url": "https://contoso.sharepoint.com/sites/Procurement/SpendReports" },
        { "url": "https://contoso.sharepoint.com/sites/Procurement/SupplierPerformance" },
        { "url": "https://contoso.sharepoint.com/sites/Procurement/Contracts" }
      ]
    },
    {
      "name": "CodeInterpreter"
    }
  ]
}
```

### 3.3 Verify CodeInterpreter is included

The `CodeInterpreter` capability is essential for this agent — it enables data analysis and visualization. Ensure it's in your capabilities array:

```json
{
  "name": "CodeInterpreter"
}
```

No additional configuration is needed for CodeInterpreter.

### 3.4 Update the instructions

Copy the content from `instructions.md` into the `instructions` field of the manifest.

---

## Step 4: Prepare the App Package

Your `appPackage` folder should contain:

```
appPackage/
├── manifest.json           # M365 app manifest
├── declarativeAgent.json   # Declarative agent manifest (from Step 3)
├── color.png              # 192x192 color icon
└── outline.png            # 32x32 outline icon
```

### 4.1 Update manifest.json

Open `manifest.json` and update:

1. **`id`**: Generate a new GUID
2. **`name.short`**: Display name (e.g., "Spend Analyst")
3. **`name.full`**: Full name (e.g., "Procurement Spend Analyst")
4. **`description.short`**: Brief description
5. **`description.full`**: Detailed description

### 4.2 Add icons

Replace placeholder icons with branded versions or use defaults.

---

## Step 5: Deploy the Agent

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
4. Add SharePoint knowledge sources
5. **Enable Code Interpreter capability**
6. Copy instructions from `instructions.md`
7. Add conversation starters
8. Publish the agent

### Option C: Manual Upload (Admin)

1. Zip the contents of the `appPackage` folder
2. Go to [Microsoft 365 Admin Center](https://admin.microsoft.com)
3. Navigate to **Settings** > **Integrated Apps**
4. Upload and deploy

---

## Step 6: Test the Agent

### 6.1 Access the agent

1. Open Microsoft 365 Copilot at https://m365.cloud.microsoft/chat
2. Click the conversation drawer icon
3. Find and select **Procurement Spend Analyst**

### 6.2 Test with conversation starters

| Starter | What to test |
|---------|--------------|
| "Summarize our procurement spend for [period]" | Basic spend analysis |
| "Who are our top 10 suppliers by spend?" | Supplier ranking |
| "Break down spend by category" | Category analysis |
| "Compare performance of [A] vs [B]" | Supplier comparison |
| "Where are savings opportunities?" | Opportunity identification |
| "How has spend changed over time?" | Trend analysis |

### 6.3 Test data analysis capabilities

Try requests that require calculation:
- "What percentage of spend is with our top 5 suppliers?"
- "Calculate the average PO value by category"
- "Show me a chart of monthly spend trends"

### 6.4 Verify behavior

- [ ] Agent finds and reads spend data files
- [ ] Agent performs calculations correctly
- [ ] Agent generates visualizations when appropriate
- [ ] Agent clearly states data limitations and assumptions
- [ ] Agent doesn't make vendor recommendations (stays analytical)

---

## Step 7: Roll Out to Users

### 7.1 Set expectations

Communicate to users:
- Agent analyzes **stored data** — not real-time ERP data
- Always verify critical numbers against source systems
- Agent provides insights, not decisions
- Data freshness depends on upload frequency

### 7.2 Training recommendations

- How to ask effective analysis questions
- Understanding data limitations
- When to verify results in source systems
- How to export or use analysis results

### 7.3 Data maintenance

Establish a process for:
- Regular spend data uploads/refreshes
- Supplier performance data updates
- Archiving old data
- Data quality checks

---

## Troubleshooting

| Issue | Possible Cause | Solution |
|-------|---------------|----------|
| "Can't find spend data" | SharePoint URLs incorrect or data not uploaded | Verify URLs; check file locations |
| Calculations seem wrong | Data format issues or missing columns | Check data structure; ensure consistent formatting |
| No visualizations | CodeInterpreter not enabled | Verify CodeInterpreter in capabilities |
| Slow responses | Large data files | Consider summarizing data before upload; use date filters |
| Outdated analysis | Stale data in SharePoint | Upload fresh data extracts; note data date |

---

## Optional Enhancements

### Connect to ERP via Graph Connector

If your organization has a Graph connector for your ERP or procurement system:

```json
{
  "name": "GraphConnectors",
  "connections": [
    { "connection_id": "your-erp-connector-id" }
  ]
}
```

This enables more real-time data access.

### Automated Data Refresh

Consider setting up:
- Power Automate flows to export ERP data to SharePoint
- Scheduled reports from your procurement system
- Automated archiving of old data

### Category-Specific Variants

For large organizations, consider variants:
- IT Spend Analyst (scoped to IT procurement data)
- Facilities Spend Analyst (scoped to facilities/MRO)
- Services Spend Analyst (scoped to professional services)

---

## Support

- **Blueprint issues**: Open an issue in the Agent Universe repository
- **Deployment issues**: Contact your Microsoft 365 administrator
- **Data questions**: Work with your procurement/finance data team
