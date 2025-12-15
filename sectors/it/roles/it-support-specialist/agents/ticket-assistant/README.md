# IT Ticket Assistant

**Type:** Assistant (Drafting Agent)  
**Role:** IT Support Specialist  
**Sector:** Information Technology  
**Complexity:** Medium  
**Deployment Time:** 45 minutes

---

## What It Does

The IT Ticket Assistant helps IT support specialists draft ticket documentation, user communications, and support materials. Instead of writing notes and emails from scratch for every ticket, technicians describe what happened and the agent generates professional, consistent content for review.

---

## Problem It Solves

| Friction Point | Impact | How Agent Helps |
|----------------|--------|-----------------|
| **Manual documentation** | 3-5 hrs/week writing notes | Generates draft notes instantly |
| **Repetitive responses** | Same emails written repeatedly | Creates consistent, professional responses |
| **Reporting overhead** | Time spent on weekly summaries | Analyzes data and produces reports |

**Key Stat:** The rule in IT support is "if it isn't in the ticket, it never happened" — but documentation takes time away from helping users. This agent helps maintain documentation standards without the time burden.

---

## Example Queries

```
"Write ticket notes for: user couldn't print, printer was offline 
 because it was unplugged, I reconnected it"

"Help me write an email explaining that the Outlook issue was 
 caused by a corrupted profile and we fixed it"

"Create an escalation summary for Tier 2: laptop won't boot 
 past Windows logo, tried safe mode and startup repair"

"Draft a KB article for fixing Teams camera issues caused 
 by Windows privacy settings"

"Analyze this ticket export and create a weekly summary"
```

---

## Requirements

- Microsoft 365 Copilot license
- SharePoint site(s) with templates and policies
- OneDriveAndSharePoint + CodeInterpreter capabilities

---

## Quick Start

1. Prepare templates in SharePoint (see SETUP.md)
2. Update `manifest-template.json` with your SharePoint URLs
3. Deploy via Copilot Studio or Teams Admin Center
4. Test with sample documentation requests
5. Roll out to IT support team

**Detailed instructions:** See [SETUP.md](./SETUP.md)

---

## Files in This Package

| File | Purpose |
|------|---------|
| `blueprint.json` | Agent metadata and configuration |
| `instructions.md` | Detailed agent behavior instructions |
| `manifest-template.json` | M365 deployment manifest (customize URLs) |
| `SETUP.md` | Step-by-step deployment guide |
| `README.md` | This file |

---

## Outputs Generated

| Output Type | Use Case |
|-------------|----------|
| **Ticket Notes** | Document troubleshooting steps and resolution |
| **User Emails** | Communicate issue status and resolution to users |
| **Escalation Summaries** | Hand off tickets to Tier 2/3 with full context |
| **KB Articles** | Convert resolved tickets into reusable knowledge |
| **Weekly Summaries** | Report on ticket volume, categories, and trends |

---

## Limitations

- Cannot submit tickets or send emails directly—generates drafts for review
- Cannot access live ITSM systems (ServiceNow, Jira)
- All outputs should be reviewed before use
- Quality depends on context provided and templates available

---

## Success Metrics

| Metric | Target |
|--------|--------|
| Documentation time reduction | 40% decrease in time spent writing notes |
| Response consistency | Improved CSAT from professional communications |
| KB contribution rate | 2x increase in new KB articles published |

---

## Related Agents

- **[Knowledge Finder](../knowledge-finder/)** — Finds solutions from the knowledge base
