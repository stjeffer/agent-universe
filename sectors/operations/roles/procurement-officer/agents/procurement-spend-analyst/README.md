# Procurement Spend Analyst

A Microsoft 365 Copilot declarative agent that helps procurement officers analyze spend data, summarize supplier performance, identify savings opportunities, and prepare reports.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Procurement Officer |
| **Complexity** | Medium |
| **Setup Time** | ~30 minutes |
| **Capabilities** | OneDriveAndSharePoint, CodeInterpreter |

## What it does

This agent transforms raw procurement data into actionable insights:

- **Summarize spend** by supplier, category, period, or department
- **Analyze trends** and identify patterns in procurement data
- **Compare suppliers** across performance metrics
- **Identify savings** opportunities and consolidation targets
- **Generate visualizations** of spend data
- **Prepare reports** for management review

## What it doesn't do

- Access live ERP data (analyzes stored data only)
- Modify source data or systems
- Recommend specific vendor decisions
- Create purchase orders or contracts

## Friction addressed

| Friction Type | Description | Time Saved |
|---------------|-------------|------------|
| Reporting overhead | Aggregating data and preparing spend reports | 2 hrs/week |
| Data analysis | Identifying trends and patterns manually | 1 hr/week |
| Supplier evaluation | Comparing supplier performance | 1 hr/week |

## Quick start

1. **Prepare** spend data in Excel/CSV format
2. **Upload** to SharePoint with supplier performance data
3. **Configure** the manifest with your SharePoint URLs
4. **Enable** CodeInterpreter capability
5. **Deploy** and test with conversation starters

See [SETUP.md](SETUP.md) for detailed instructions.

## Files

| File | Purpose |
|------|---------|
| `blueprint.json` | Structured agent definition and metadata |
| `instructions.md` | Human-readable agent instructions |
| `manifest-template.json` | M365 manifest with placeholders |
| `SETUP.md` | Step-by-step deployment guide |

## Example conversations

**Spend summary:**
> "Summarize our procurement spend for Q3"

**Supplier analysis:**
> "Who are our top 10 suppliers by spend?"

**Savings identification:**
> "Where are the biggest opportunities to reduce procurement costs?"

**Trend analysis:**
> "How has our spend with FastShip changed over the past year?"

## Data requirements

For best results, provide:
- Spend data in Excel or CSV format
- Consistent column structure (PO, Supplier, Amount, Date, Category)
- Supplier performance metrics
- Historical data for trend analysis

## Important notes

- Agent analyzes **stored data** — not real-time ERP feeds
- Verify critical numbers against source systems
- Data freshness depends on upload frequency
- CodeInterpreter capability required for calculations and charts

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to spend data and reports
- Spend data in analyzable format (Excel, CSV)
- VS Code with M365 Agents Toolkit (for deployment)
