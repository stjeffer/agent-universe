# RFP/RFQ Drafting Assistant

A Microsoft 365 Copilot declarative agent that helps procurement officers draft solicitation documents by leveraging templates, past RFPs, and organizational policies.

## Overview

| | |
|---|---|
| **Sector** | Operations |
| **Role** | Procurement Officer |
| **Complexity** | Low |
| **Setup Time** | ~25 minutes |
| **Capabilities** | OneDriveAndSharePoint |

## What it does

This agent helps procurement professionals create consistent, policy-compliant solicitation documents:

- **Draft RFPs/RFQs** using organizational templates
- **Find relevant templates** for different procurement categories
- **Write specifications** for products and services
- **Identify policy requirements** that must be included
- **Develop evaluation criteria** and scoring frameworks
- **Reference past solicitations** to leverage proven approaches

## What it doesn't do

- Create final documents (produces drafts only)
- Recommend specific vendors or products
- Set budgets or suggest pricing
- Send documents to vendors
- Replace legal review for complex solicitations

## Friction addressed

| Friction Type | Description | Time Saved |
|---------------|-------------|------------|
| Manual document creation | Drafting RFPs from scratch each time | 3-4 hrs/week |
| Compliance verification | Ensuring required policy language is included | 1 hr/week |
| Information seeking | Finding relevant templates and past RFPs | 1 hr/week |

## Quick start

1. **Identify** your SharePoint locations for templates, policies, and past RFPs
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

**Starting an RFP:**
> "Help me draft an RFP for office furniture"

**Finding templates:**
> "What RFP templates do we have for IT services?"

**Policy requirements:**
> "What policy language must be included for an RFP over $100,000?"

**Referencing past work:**
> "Show me how we handled delivery requirements in past furniture RFPs"

## Important notes

- All generated content is **draft material** requiring human review
- Users should verify templates are current before using
- Legal review recommended for high-value or complex solicitations
- Agent cites sources but users should verify accuracy

## Requirements

- Microsoft 365 Copilot license
- SharePoint access to procurement templates and policies
- VS Code with M365 Agents Toolkit (for deployment)
