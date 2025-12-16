# Content Assistant

**Type:** Drafting Agent
**Role:** Content Marketer
**Sector:** Marketing

## Overview

Content Assistant helps Content Marketers draft content pieces more efficiently while maintaining brand voice and editorial standards. It creates outlines, briefs, social media posts, newsletter drafts, and performance summaries based on organizational templates and guidelines.

## Problem Solved

Content Marketers spend 8-12 hours per week on manual content creation, often starting from scratch when similar content already exists. This agent accelerates drafting time while ensuring consistent brand voice and formatting.

**Important:** All output is marked as DRAFT and requires human review before publication.

## Capabilities

- ✅ Draft blog post outlines and structures
- ✅ Create content briefs for writers
- ✅ Generate social media post variations
- ✅ Draft newsletter sections
- ✅ Create content performance summaries
- ✅ Generate meta descriptions and SEO elements
- ✅ Build content repurposing plans

## Limitations

- ❌ Cannot publish or schedule content
- ❌ Does not create final visual designs
- ❌ Cannot make strategic content decisions
- ❌ Does not approve content for publication
- ❌ Cannot invent statistics or factual claims

## Quick Start

1. Review the [SETUP.md](SETUP.md) guide
2. **Critical:** Ensure brand voice guidelines are documented
3. Configure SharePoint URLs in the manifest
4. Deploy via Copilot Studio or Teams Admin
5. Test with sample content requests

## Sample Queries

```
"Create a blog outline about content marketing ROI"
"Draft a content brief for an ebook on customer success"
"Write social media posts for our new blog about SEO trends"
"Create a newsletter section summarizing this month's content"
"Draft a quarterly content performance summary"
```

## Data Sources Required

| Source | Required | Description |
|--------|----------|-------------|
| Brand Guidelines | Yes | Style guide, brand voice, messaging framework |
| Content Templates | Yes | Blog templates, brief formats |
| Content Library | No | Published content for reference |
| Performance Data | No | Analytics for reporting features |

## Time Savings

**Estimated:** 4-6 hours per week

- Faster first drafts
- Consistent formatting
- Reduced revision cycles
- Better brand voice compliance

## Output Quality Factors

The agent's output quality depends heavily on:

1. **Brand Guidelines Completeness** - The more detailed your voice documentation, the better the output
2. **Template Quality** - Clear templates with examples produce better results
3. **Reference Content** - Published examples help the agent learn your style

## Files

- `blueprint.json` - Agent metadata and configuration
- `instructions.md` - Detailed agent behavior instructions
- `manifest-template.json` - M365 deployment manifest
- `SETUP.md` - Step-by-step deployment guide
- `README.md` - This file

## Important Notes

⚠️ **All output is DRAFT** - Never publish agent output without human review

⚠️ **No fabrication** - The agent will not invent statistics or quotes; it uses placeholders like [STAT NEEDED]

⚠️ **Brand guidelines are critical** - Invest time in documentation for best results
