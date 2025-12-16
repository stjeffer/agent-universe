# Content Finder

**Type:** Retrieval Agent
**Role:** Content Marketer
**Sector:** Marketing

## Overview

Content Finder helps Content Marketers quickly locate existing content assets, brand guidelines, style documentation, and reference materials across organizational content libraries. Instead of manually searching through folders or asking colleagues, users can ask natural language questions to find what they need.

## Problem Solved

Content Marketers spend 4-6 hours per week searching for existing content assets, brand guidelines, and reference materials scattered across systems. This agent reduces that time by providing instant access to organizational content through conversational search.

## Capabilities

- ✅ Search content libraries by topic, format, or date
- ✅ Retrieve brand voice and style guidelines
- ✅ Find approved messaging and positioning statements
- ✅ Locate content for repurposing opportunities
- ✅ Answer questions about brand standards
- ✅ Find content templates and formatting guides
- ✅ Surface content performance data

## Limitations

- ❌ Cannot create new content
- ❌ Cannot modify or delete existing content
- ❌ Does not provide strategic recommendations
- ❌ Cannot access external/competitor content

## Quick Start

1. Review the [SETUP.md](SETUP.md) guide
2. Configure SharePoint URLs in the manifest
3. Deploy via Copilot Studio or Teams Admin
4. Test with sample queries

## Sample Queries

```
"Find all blog posts about customer success from this year"
"What's our approved messaging for the product launch?"
"Show me the brand voice guidelines for social media"
"Do we have any existing content about SEO best practices?"
"Where's the template for content briefs?"
```

## Data Sources Required

| Source | Required | Description |
|--------|----------|-------------|
| Content Library | Yes | Published blog posts, articles, ebooks |
| Brand Guidelines | Yes | Style guide, brand voice documentation |
| Content Templates | No | Blog templates, brief templates |
| Editorial Calendar | No | Content planning documents |

## Time Savings

**Estimated:** 3-5 hours per week

- Faster asset discovery
- Reduced repeat questions to team leads
- Higher content repurposing rate

## Files

- `blueprint.json` - Agent metadata and configuration
- `instructions.md` - Detailed agent behavior instructions
- `manifest-template.json` - M365 deployment manifest
- `SETUP.md` - Step-by-step deployment guide
- `README.md` - This file
