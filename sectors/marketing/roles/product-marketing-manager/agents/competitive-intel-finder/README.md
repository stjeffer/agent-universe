# Competitive Intel Finder

A retrieval agent that helps Product Marketing Managers quickly find competitive intelligence from organizational knowledge repositories.

## Overview

| Attribute | Value |
|-----------|-------|
| **Type** | Retrieval |
| **Role** | Product Marketing Manager |
| **Sector** | Marketing |
| **Complexity** | Low |
| **Setup Time** | ~30 minutes |

## Problem Solved

Product Marketing Managers spend 4-6 hours per week searching for competitive intelligence scattered across battlecards, win/loss reports, analyst documents, and internal wikis. This agent consolidates access to competitive intelligence, enabling PMMs to quickly answer sales questions and prepare for competitive situations.

## Capabilities

- ✅ Search competitive battlecards by competitor name
- ✅ Retrieve win/loss analysis data
- ✅ Find pricing and packaging intelligence
- ✅ Surface objection handling guidance
- ✅ Locate analyst reports and market research
- ✅ Flag outdated information

## Data Sources Required

1. **Competitive Battlecards** (SharePoint) - Required
2. **Win/Loss Analysis** (SharePoint) - Required
3. **Market Research** (SharePoint) - Optional
4. **PMM Knowledge Base** (SharePoint) - Required

## Example Queries

```
"What are our key differentiators against [Competitor]?"
"Find recent win/loss data against [Competitor]"
"What pricing does [Competitor] use?"
"How should we position against [Competitor] for security buyers?"
"What objections do sales encounter with [Competitor]?"
```

## Quick Start

1. Prepare SharePoint libraries with competitive content
2. Copy SharePoint URLs for each library
3. Update `manifest-template.json` with your URLs
4. Deploy via Copilot Studio
5. Test with sample queries

See `SETUP.md` for detailed instructions.

## Files

| File | Purpose |
|------|---------|
| `blueprint.json` | Agent metadata and configuration |
| `instructions.md` | Detailed agent behavior instructions |
| `manifest-template.json` | M365 Copilot deployment manifest |
| `SETUP.md` | Step-by-step deployment guide |
| `README.md` | This file |

## Estimated Impact

- **Time Saved**: 3-5 hours/week
- **Primary Benefit**: Faster competitive response for sales team
- **Secondary Benefit**: More consistent competitive messaging
