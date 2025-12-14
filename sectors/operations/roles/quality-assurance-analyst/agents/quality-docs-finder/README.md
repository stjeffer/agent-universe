# Quality Docs Finder

A Microsoft 365 Copilot declarative agent that helps QA analysts find specifications, standards, SOPs, and compliance documentation.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Quality Assurance Analyst |
| **Complexity** | Low |
| **Setup Time** | ~25 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

- **Find SOPs** — procedures, work instructions
- **Locate specifications** — product, material, process
- **Look up supplier records** — quality data, certifications
- **Check calibration status** — equipment schedules
- **Find audit documents** — reports, findings, evidence

## What it doesn't do

- Modify documents or records
- Approve quality decisions
- Access live QMS data (uses documents)

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Information seeking (specs, SOPs) | 2 hrs/week |
| Compliance tracking | 1 hr/week |
| Supplier quality lookup | 1 hr/week |

## Quick start

1. **Identify** SharePoint locations with quality documentation
2. **Configure** manifest with URLs
3. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "Find the SOP for incoming inspection"

> "What's the specification for Part Number 12345?"

> "Find the quality records for supplier MetalWorks Inc."

> "When is the CMM due for calibration?"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to quality documentation
