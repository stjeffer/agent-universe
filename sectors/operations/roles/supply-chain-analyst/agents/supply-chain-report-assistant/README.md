# Supply Chain Report Assistant

A Microsoft 365 Copilot declarative agent that helps supply chain analysts create reports, summarize KPIs, and prepare management updates.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Supply Chain Analyst |
| **Complexity** | Medium |
| **Setup Time** | ~30 minutes |
| **Capabilities** | OneDriveAndSharePoint, CodeInterpreter |

## What it does

- **Create performance summaries** — weekly/monthly reports
- **Calculate KPIs** — inventory turns, OTIF, fill rate, cycle time
- **Analyze trends** — compare periods, identify patterns
- **Draft executive updates** — concise summaries for leadership
- **Visualize data** — charts and tables from supply chain data

## What it doesn't do

- Modify source data or systems
- Publish reports automatically
- Access live ERP data (uses document exports)
- Make business recommendations

## Friction addressed

| Friction Type | Description | Time Saved |
|---------------|-------------|------------|
| Reporting overhead | Manual report creation and formatting | 2 hrs/week |
| Manual document creation | Building dashboards and summaries | 1 hr/week |

## Quick start

1. **Prepare** data exports in Excel/CSV format
2. **Upload** to SharePoint with templates and KPI definitions
3. **Configure** manifest with URLs and enable CodeInterpreter
4. **Deploy** and test with conversation starters

See [SETUP.md](SETUP.md) for details.

## Example conversations

**Weekly summary:**
> "Create a weekly supply chain performance summary"

**KPI analysis:**
> "Analyze inventory turns and days of supply from the latest data"

**Executive update:**
> "Draft an executive summary of supply chain performance"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to data exports
- Data in Excel or CSV format
