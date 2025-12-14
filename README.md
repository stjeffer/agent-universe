# 🌌 Agent Universe

**A research-driven catalog of Microsoft 365 Copilot declarative agents, organized by industry sector and role.**

Stop guessing what AI agents to build. Start with evidence.

---

## The Problem

Everyone's excited about AI agents. But when it comes to actually building them, teams face the same questions:

- *"What agent should we build for [role]?"*
- *"What would it actually do?"*
- *"How do we know it'll be useful?"*

Most agent development starts with technology ("let's connect Copilot to SharePoint!") rather than human need ("what's eating 4 hours of this person's week?").

The result? Agents that demo well but don't get adopted.

## The Solution

Agent Universe flips the script. Every agent in this catalog is built on a foundation of:

| Layer | What It Is | Why It Matters |
|-------|-----------|----------------|
| **Role Research** | 15-50 sources per role (job postings, pain point articles, industry guides) | Grounds agents in real work, not assumptions |
| **Task Analysis** | Time-allocation breakdown of what the role actually does | Identifies where friction lives |
| **Friction Mapping** | Specific pain points with time impact and automation potential | Prioritizes what to solve |
| **Agent Blueprints** | Complete, deployment-ready agent packages | Ship in 30 minutes, not 30 days |

---

## 📊 What's Inside

### Current Coverage

| Sector | Roles | Agents | Total Time Saved |
|--------|-------|--------|------------------|
| **Operations** | 5 | 11 | ~38 hrs/week |

### Operations Sector

| Role | Agents | Key Friction Solved |
|------|--------|---------------------|
| **Procurement Officer** | Contract & Supplier Finder | Finding past contracts, pricing history, supplier records |
| | RFP/RFQ Drafting Assistant | Creating solicitation documents from templates and policies |
| | Procurement Spend Analyst | Analyzing spend data and preparing procurement reports |
| **Supply Chain Analyst** | Inventory & Order Tracker | Finding inventory status, order info, shipment tracking |
| | Supply Chain Report Assistant | Drafting KPI reports and management updates |
| **Facilities Manager** | Maintenance & Service Finder | Finding maintenance records, vendor info, compliance docs |
| | Space & Asset Lookup | Finding room info, equipment locations, asset details |
| **Operations Manager** | Operations Status Finder | Finding cross-departmental status and project updates |
| | Operations Report Assistant | Drafting performance reports and leadership updates |
| **QA Analyst** | Quality Docs Finder | Finding specs, SOPs, standards, supplier quality records |
| | Quality Report Assistant | Drafting quality reports, NCR summaries, CAPA status |

---

## 🏗️ Repository Structure

```
agent-universe/
├── catalog.json                    # Master index of all agents
├── config/
│   ├── sectors.json               # Sector definitions
│   ├── friction-types.json        # Friction taxonomy
│   └── capabilities.json          # M365 Copilot capabilities
├── schemas/
│   └── blueprint.schema.json      # Agent blueprint schema
└── sectors/
    └── operations/
        ├── _sector.json
        └── roles/
            └── [role-name]/
                ├── _role.json           # Role profile & friction analysis
                ├── ANALYSIS.md          # Full research methodology
                ├── job-evidence.csv     # Source documentation
                └── agents/
                    └── [agent-name]/
                        ├── blueprint.json         # Agent metadata
                        ├── instructions.md        # Human-readable instructions
                        ├── manifest-template.json # M365 deployment manifest
                        ├── SETUP.md              # Step-by-step setup guide
                        └── README.md             # Quick reference
```

---

## 🚀 Quick Start

### Deploy an Agent (30 minutes)

1. **Browse the catalog** → Find an agent that matches your need
2. **Check prerequisites** → Ensure you have the required SharePoint content
3. **Configure the manifest** → Update `manifest-template.json` with your URLs
4. **Deploy** → Use M365 Agents Toolkit or Copilot Studio
5. **Test & refine** → Verify with real queries

### Example: Deploy the Contract & Supplier Finder

```bash
# Clone the repo
git clone https://github.com/[your-org]/agent-universe.git
cd agent-universe/sectors/operations/roles/procurement-officer/agents/contract-supplier-finder

# Copy and configure the manifest
cp manifest-template.json declarativeAgent.json
# Edit declarativeAgent.json with your SharePoint URLs

# Deploy via M365 Agents Toolkit (VS Code)
# Or import into Copilot Studio
```

---

## 📐 Design Philosophy

### Why "Helper" Agents?

Every agent in this catalog follows a deliberate pattern: **retrieve information** or **draft content**. They help humans work faster — they don't automate workflows end-to-end.

Why?

| Consideration | Our Approach |
|---------------|--------------|
| **Process variation** | A procurement workflow at a 50-person startup vs. a 5,000-person enterprise vs. a government agency looks completely different. Retrieval works everywhere. |
| **Integration complexity** | Action-taking agents require API access, approval logic, error handling — that's custom development, not a shareable blueprint. |
| **Trust & adoption** | Humans stay in the loop. The agent accelerates; the human decides. |
| **Time to value** | Configure SharePoint URLs and deploy in 30 minutes. No custom code required. |

**These agents are starting points, not endpoints.** Organizations can extend them with actions, connectors, and custom logic as needed.

### The Friction-First Method

```
┌─────────────────┐
│  Role Research  │  ← 15-50 sources: job postings, pain points, industry guides
└────────┬────────┘
         ▼
┌─────────────────┐
│  Task Clusters  │  ← What does this role actually do? In what proportions?
└────────┬────────┘
         ▼
┌─────────────────┐
│ Friction Points │  ← Where is time being wasted? What's automatable?
└────────┬────────┘
         ▼
┌─────────────────┐
│ Agent Blueprints│  ← Targeted solutions with measurable value
└─────────────────┘
```

Every agent traces back to documented evidence. No guessing.

---

## 📁 Agent Anatomy

Each agent package contains everything needed to understand, deploy, and customize:

### `blueprint.json`
Structured metadata including friction addressed, capabilities required, setup complexity, and governance considerations.

### `instructions.md`
Human-readable agent instructions with:
- Role definition and scope
- Guardrails and boundaries  
- Response style guidance
- Detailed examples of good interactions
- Boundary handling (what happens when users ask for things outside scope)

### `manifest-template.json`
Ready-to-deploy M365 Copilot manifest. Replace placeholder URLs with your SharePoint locations.

### `SETUP.md`
Step-by-step deployment guide with:
- Prerequisites checklist
- Knowledge source identification
- Configuration walkthrough
- Testing scenarios
- Troubleshooting tips

---

## 🔍 Finding Agents

### By Sector
```
sectors/[sector-name]/roles/
```

### By Role
```
catalog.json → index.by_role
```

### By Friction Type
```
catalog.json → index.by_friction
```

### By Capability
```
catalog.json → index.by_capability
```

---

## 📈 Measuring Value

Each agent includes estimated time savings based on:

| Factor | How We Estimate |
|--------|-----------------|
| **Friction frequency** | How often does this task occur? (daily/weekly/monthly) |
| **Time per occurrence** | How long does it take without the agent? |
| **Automation potential** | How much can the agent realistically help? |

**These are estimates, not guarantees.** Actual value depends on:
- Quality of your SharePoint content
- User adoption and query patterns
- Organizational context

We recommend tracking actual usage and gathering feedback to measure real impact.

---

## 🛣️ Roadmap

### Current
- [x] Operations sector (5 roles, 11 agents)

### Planned
- [ ] Finance sector (Accountant, Financial Analyst, Controller)
- [ ] Human Resources sector (HR Generalist, Recruiter, L&D Specialist)
- [ ] Sales sector (Account Executive, Sales Operations, Sales Engineer)
- [ ] Marketing sector (Content Marketer, Product Marketing, Demand Gen)
- [ ] IT sector (IT Support, Systems Administrator, Security Analyst)

### Future
- [ ] Agent effectiveness measurement framework
- [ ] Customization patterns and extension guides
- [ ] Cross-role agent patterns
- [ ] Industry-specific variants (Healthcare, Manufacturing, Financial Services)

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to Contribute

| Contribution | Impact |
|--------------|--------|
| **Validate research** | "I'm a Procurement Officer and this matches/misses my experience" |
| **Add sources** | Additional job postings, pain point articles, industry research |
| **Improve instructions** | Better examples, edge cases, guardrails |
| **New roles** | Research and blueprint new roles within existing sectors |
| **New sectors** | Expand coverage to new industry sectors |
| **Test & feedback** | Deploy agents and share what worked/didn't |

### Research Standards

New roles should include:
- Minimum 15 documented sources in `job-evidence.csv`
- Task cluster analysis with time allocation
- Friction mapping with time impact estimates
- At least one agent addressing high-priority friction

---

## 📜 License

MIT License — use freely, attribution appreciated.

---

## 🙏 Acknowledgments

This catalog was built by analyzing hundreds of job descriptions, industry articles, and practitioner perspectives. We're grateful to the professionals who share their experiences openly — your insights make this possible.

---

<div align="center">

**Stop building agents based on assumptions.**

**Start building agents based on evidence.**

[Browse the Catalog](#-whats-inside) · [Deploy Your First Agent](#-quick-start) · [Contribute](#-contributing)

</div>
