# Space & Asset Lookup

A Microsoft 365 Copilot declarative agent that helps find information about building spaces, rooms, and equipment locations.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Facilities Manager |
| **Complexity** | Low |
| **Setup Time** | ~20 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

- **Find room information** — capacity, AV equipment, features
- **Locate equipment** — where assets are located
- **Access floor plans** — building layouts
- **Look up asset details** — specifications, purchase info

## What it doesn't do

- Book rooms or manage calendars
- Modify asset records
- Access real-time occupancy data

## Friction addressed

| Friction Type | Time Saved |
|---------------|------------|
| Information seeking (space/asset info) | 2 hrs/week |

## Quick start

1. **Identify** SharePoint locations with floor plans, room inventory, asset register
2. **Configure** manifest with URLs
3. **Deploy** and test

See [SETUP.md](SETUP.md) for details.

## Example conversations

> "What's the capacity of conference room Cascade?"

> "Where is the large format printer located?"

> "Which conference rooms have video conferencing?"

> "What do we know about asset EQ-2023-0088?"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to space and asset documentation
