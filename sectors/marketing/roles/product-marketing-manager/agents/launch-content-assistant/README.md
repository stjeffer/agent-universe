# Launch Content Assistant

A drafting agent that helps Product Marketing Managers create launch communications, sales enablement content, and competitive summaries using approved organizational messaging.

## Overview

| Attribute | Value |
|-----------|-------|
| **Type** | Drafting |
| **Role** | Product Marketing Manager |
| **Sector** | Marketing |
| **Complexity** | Medium |
| **Setup Time** | ~45 minutes |

## Problem Solved

Product Marketing Managers spend 6-10 hours per week creating and updating sales enablement content. Research shows that 65% of marketing assets go unused because they're not relevant or timely. This agent accelerates content creation while ensuring alignment with approved positioning and messaging frameworks.

## Capabilities

- ✅ Draft internal launch announcements
- ✅ Create competitive comparison tables
- ✅ Write sales enablement talking points
- ✅ Generate battlecard updates
- ✅ Build feature-benefit statements
- ✅ Draft launch timeline summaries
- ✅ Create sales enablement emails

## Data Sources Required

1. **Positioning & Messaging** (SharePoint) - Required
2. **Launch Templates** (SharePoint) - Required
3. **Product Documentation** (SharePoint) - Required
4. **Competitive Battlecards** (SharePoint) - Optional

## Example Queries

```
"Draft an internal launch announcement for [feature name]"
"Create a competitive comparison table for [competitor] vs our [product]"
"Write sales enablement talking points for [new feature]"
"Update the [competitor] battlecard with our new [capability]"
"Draft an email to sales about the upcoming [feature] launch"
```

## Quick Start

1. Ensure positioning and messaging documents exist in SharePoint
2. Create or identify launch templates library
3. Copy SharePoint URLs for each library
4. Update `manifest-template.json` with your URLs
5. Deploy via Copilot Studio
6. Test with sample drafting requests

See `SETUP.md` for detailed instructions.

## Important Notes

- **All output is DRAFT** - requires PMM review before use
- Agent uses only approved positioning from source documents
- Customer-facing content needs additional legal/compliance review
- Agent cites sources used for transparency

## Files

| File | Purpose |
|------|---------|
| `blueprint.json` | Agent metadata and configuration |
| `instructions.md` | Detailed agent behavior instructions |
| `manifest-template.json` | M365 Copilot deployment manifest |
| `SETUP.md` | Step-by-step deployment guide |
| `README.md` | This file |

## Estimated Impact

- **Time Saved**: 4-6 hours/week
- **Primary Benefit**: Faster content creation aligned with positioning
- **Secondary Benefit**: More consistent messaging across assets
