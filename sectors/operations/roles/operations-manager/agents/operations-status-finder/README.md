# Operations Status Finder

A Microsoft 365 Copilot declarative agent that helps operations managers find status updates, project information, and cross-departmental updates.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Operations Manager |
| **Complexity** | Low |
| **Setup Time** | ~25 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

- **Find project status** — current state, progress, blockers
- **Locate team updates** — meeting notes, weekly reports
- **Summarize departmental activity** — cross-functional view
- **Identify issues** — blockers, escalations, risks
- **Prepare for meetings** — gather relevant context

## What it doesn't do

- Update project status or documents
- Send communications or notifications
- Access live project management systems (uses documents)

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Information seeking (cross-departmental) | 2 hrs/week |
| Context switching | 1 hr/week |
| Stakeholder communication prep | 1 hr/week |

## Quick start

1. **Identify** SharePoint locations with status reports and team updates
2. **Configure** manifest with URLs
3. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "What's the current status of the warehouse expansion project?"

> "What are the latest updates from the Supply Chain team?"

> "Summarize the key operational updates from this week"

> "What do I need to know before my meeting with Production?"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to operational documentation
