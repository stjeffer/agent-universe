# Operations Report Assistant

A Microsoft 365 Copilot declarative agent that helps operations managers draft performance reports, KPI summaries, and leadership updates.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Operations Manager |
| **Complexity** | Medium |
| **Setup Time** | ~30 minutes |
| **Capabilities** | OneDriveAndSharePoint, CodeInterpreter |

## What it does

- **Draft operations reports** — weekly, monthly, quarterly
- **Summarize KPIs** — with comparisons and trends
- **Create executive summaries** — concise leadership updates
- **Analyze trends** — performance over time
- **Prepare meeting materials** — agendas and talking points

## What it doesn't do

- Publish or distribute reports
- Update live systems or dashboards
- Make final decisions (recommendations only)

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Reporting overhead | 2 hrs/week |
| Data analysis | 1 hr/week |
| Meeting preparation | 1 hr/week |

## Quick start

1. **Prepare** KPI data in Excel/CSV format
2. **Identify** SharePoint locations with data and templates
3. **Configure** manifest with URLs and CodeInterpreter
4. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "Help me create the weekly operations report"

> "Summarize our key operational KPIs for Q4"

> "Draft an executive summary for leadership"

> "Compare this month's performance to last month"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to operational data
- KPI data in structured format (Excel/CSV)
