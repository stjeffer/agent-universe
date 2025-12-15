# HR Document Assistant

A Microsoft 365 Copilot declarative agent that helps HR teams draft offer letters, job descriptions, onboarding documents, and employee communications.

## Overview

| | |
|---|---|
| **Sector** | Human Resources |
| **Role** | HR Generalist |
| **Complexity** | Medium |
| **Setup Time** | ~30 minutes |
| **Capabilities** | OneDriveAndSharePoint, CodeInterpreter (optional) |

## What it does

- **Draft offer letters** — using company templates
- **Create job descriptions** — following standard format
- **Write onboarding emails** — welcome messages, first-day details
- **Policy communications** — announcements and updates
- **HR reports** — metrics summaries (with CodeInterpreter)

## What it doesn't do

- Send documents or communications
- Access confidential salary data
- Finalize or approve documents
- Replace legal review for sensitive documents

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Manual document creation | 2 hrs/week |
| Reporting overhead | 1 hr/week |

## Quick start

1. **Gather** HR templates (offer letters, JDs, etc.)
2. **Organize** templates in SharePoint
3. **Configure** manifest with template URLs
4. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "Help me draft an offer letter for a Marketing Manager position"

> "Create a job description for a Customer Success Manager"

> "Draft a welcome email for a new hire starting Monday"

> "Help me communicate the new flexible work policy"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to HR templates
- Current document templates
