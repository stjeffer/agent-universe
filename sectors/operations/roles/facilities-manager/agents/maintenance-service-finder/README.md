# Maintenance & Service Finder

A Microsoft 365 Copilot declarative agent that helps facilities managers find maintenance records, vendor information, and compliance documentation.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Facilities Manager |
| **Complexity** | Low |
| **Setup Time** | ~20 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

- **Find maintenance history** for equipment and building systems
- **Locate vendor contacts** and service providers
- **Look up contracts** and service agreements
- **Find inspection records** and compliance documentation
- **Locate equipment manuals** and specifications

## What it doesn't do

- Create or modify work orders
- Contact vendors directly
- Access live CMMS data (uses documents)
- Make service recommendations

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Information seeking (maintenance records) | 2 hrs/week |
| Vendor coordination | 1 hr/week |
| Compliance tracking | 1 hr/week |

## Quick start

1. **Identify** SharePoint locations with facilities docs
2. **Configure** manifest with URLs
3. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "What's the maintenance history for HVAC Unit 3?"

> "Who do we call for elevator issues?"

> "Find our service contract with ClimateControl Inc"

> "Find the most recent fire suppression inspection report"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to facilities documentation
