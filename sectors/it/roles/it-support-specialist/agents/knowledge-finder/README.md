# IT Knowledge Finder

**Type:** Finder (Retrieval Agent)  
**Role:** IT Support Specialist  
**Sector:** Information Technology  
**Complexity:** Low  
**Deployment Time:** 30 minutes

---

## What It Does

The IT Knowledge Finder helps IT support specialists quickly locate solutions, troubleshooting guides, and documentation from the organization's knowledge base. Instead of manually searching through SharePoint sites and folders, technicians ask natural language questions and get relevant answers.

---

## Problem It Solves

| Friction Point | Impact | How Agent Helps |
|----------------|--------|-----------------|
| **Information seeking** | 4-8 hrs/week wasted searching | Searches multiple KB sources instantly |
| **Knowledge fragmentation** | Tribal knowledge lost when staff leave | Surfaces documented solutions systematically |
| **Slow resolution times** | Users wait while techs search | Reduces search time by 50%+ |

**Key Stat:** IT employees spend an average of **4.2 hours per day** looking for information (Document360). This agent targets that waste directly.

---

## Example Queries

```
"Find the resolution steps for error 0x80070005"

"What's the procedure for setting up VPN on Mac?"

"Have we seen Outlook crashes in Finance before?"

"What's the IP address for the backup domain controller?"

"How do I enroll a new device in Intune?"
```

---

## Requirements

- Microsoft 365 Copilot license
- SharePoint site(s) with IT knowledge base content
- OneDriveAndSharePoint capability enabled

---

## Quick Start

1. Prepare your SharePoint KB content (see SETUP.md)
2. Update `manifest-template.json` with your SharePoint URLs
3. Deploy via Copilot Studio or Teams Admin Center
4. Test with common queries
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

## Limitations

- Cannot access live ITSM systems (ServiceNow, Jira) — only SharePoint content
- Cannot execute fixes or make system changes
- Cannot access external websites or vendor portals
- Quality depends on knowledge base content quality

---

## Success Metrics

| Metric | Target |
|--------|--------|
| Search time reduction | 50% decrease in time spent finding solutions |
| First-call resolution | 15% increase in Tier 1 resolution rate |
| Knowledge reuse | 30% increase in KB article utilization |

---

## Related Agents

- **[Ticket Assistant](../ticket-assistant/)** — Drafts ticket notes and user communications
