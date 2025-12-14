# Quality Report Assistant

A Microsoft 365 Copilot declarative agent that helps QA analysts draft quality reports, summarize NCR data, and analyze quality metrics.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Quality Assurance Analyst |
| **Complexity** | Medium |
| **Setup Time** | ~30 minutes |
| **Capabilities** | OneDriveAndSharePoint, CodeInterpreter |

## What it does

- **Draft quality reports** — monthly, quarterly summaries
- **Summarize NCRs** — by category, disposition, trend
- **Track CAPAs** — status, overdue, effectiveness
- **Analyze trends** — quality metrics over time
- **Prepare audit docs** — findings summaries

## What it doesn't do

- Publish or distribute reports
- Close CAPAs or approve quality decisions
- Update live QMS systems

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Manual document creation | 1.5 hrs/week |
| Reporting overhead | 1 hr/week |
| NCR/CAPA tracking | 0.5 hrs/week |

## Quick start

1. **Prepare** quality data in Excel/CSV format
2. **Identify** SharePoint locations with NCR/CAPA logs
3. **Configure** manifest with URLs and CodeInterpreter
4. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "Help me create the monthly quality report"

> "Summarize non-conformances for Q4 2024"

> "What's the status of open CAPAs?"

> "What are the top defect types this month?"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to quality data
- Quality metrics in structured format (Excel/CSV)
