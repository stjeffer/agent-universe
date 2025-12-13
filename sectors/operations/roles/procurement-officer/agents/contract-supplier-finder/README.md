# Contract & Supplier Finder

A Microsoft 365 Copilot declarative agent that helps procurement officers quickly find past contracts, supplier information, pricing history, and performance records.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Procurement Officer |
| **Complexity** | Low |
| **Setup Time** | ~20 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

This agent helps procurement professionals find information scattered across SharePoint without manual searching:

- **Find contracts** by supplier name, category, or date
- **Locate supplier information** including contacts, profiles, and documentation
- **Retrieve pricing history** for negotiation preparation
- **Identify expiring contracts** approaching renewal windows
- **Access RFP responses** from past solicitations
- **Review supplier performance** evaluations and scorecards

## What it doesn't do

- Create, edit, or modify contracts
- Make recommendations on supplier selection
- Provide legal advice
- Access systems outside configured SharePoint locations

## Friction addressed

| Friction Type | Description | Time Saved |
|---------------|-------------|------------|
| Information seeking | Finding contracts and supplier data across multiple locations | 2-3 hrs/week |
| Contract tracking | Locating contracts approaching renewal | 1 hr/week |
| Context switching | Gathering vendor history from multiple sources | 1 hr/week |

## Quick start

1. **Identify** your SharePoint locations for contracts, suppliers, and RFP responses
2. **Configure** the manifest template with your URLs
3. **Deploy** using M365 Agents Toolkit or Copilot Studio
4. **Test** with the conversation starters

See [SETUP.md](SETUP.md) for detailed instructions.

## Files

| File | Purpose |
|------|---------|
| `blueprint.json` | Structured agent definition and metadata |
| `instructions.md` | Human-readable agent instructions |
| `manifest-template.json` | M365 manifest with placeholders |
| `SETUP.md` | Step-by-step deployment guide |

## Example conversations

**Finding a contract:**
> "Find our current contract with Acme Office Supplies"

**Pricing history:**
> "What pricing have we had with FastShip Logistics over the past 2 years?"

**Expiring contracts:**
> "Which contracts are expiring in the next 90 days?"

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to procurement documentation
- VS Code with M365 Agents Toolkit (for deployment)
