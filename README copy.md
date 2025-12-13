# Copilot Agent Universe

A searchable catalog of Microsoft 365 Copilot declarative agent blueprints, organized by sector and role.

## What is this?

This repository contains **agent blueprints** — templates for Microsoft 365 Copilot declarative agents that can be configured and deployed to any customer tenant. Each blueprint includes:

- **Instructions** — The behavioral guidance for the agent
- **Conversation starters** — Example prompts to help users get started
- **Setup guide** — Step-by-step deployment instructions
- **Manifest template** — M365 declarative agent manifest with placeholders for tenant-specific configuration

## Structure

```
agent-universe/
├── catalog.json                 # Master searchable index of all agents
├── config/                      # Global configuration
│   ├── sectors.json            # Sector definitions
│   ├── friction-types.json     # Friction taxonomy
│   └── capabilities.json       # M365 capability definitions
├── schemas/                     # JSON schemas for validation
├── sectors/                     # Agent blueprints organized by sector
│   └── {sector}/
│       └── roles/
│           └── {role}/
│               ├── _role.json  # Role profile and friction analysis
│               └── agents/
│                   └── {agent}/
│                       ├── blueprint.json
│                       ├── instructions.md
│                       ├── SETUP.md
│                       ├── manifest-template.json
│                       └── README.md
└── tools/                       # Utility scripts
```

## How to use

### Finding an agent

1. Browse the `catalog.json` file or use the search tool
2. Filter by sector, role, friction type, or capability
3. Review the agent's README and blueprint

### Deploying an agent

1. Navigate to the agent folder (e.g., `sectors/operations/roles/procurement-officer/agents/contract-supplier-finder/`)
2. Read `SETUP.md` for prerequisites and configuration steps
3. Copy `manifest-template.json` and fill in tenant-specific values (SharePoint URLs, etc.)
4. Deploy using Microsoft 365 Agents Toolkit or Copilot Studio

## Sectors

| Sector | Description |
|--------|-------------|
| Operations | Procurement, supply chain, facilities, logistics |
| Finance | FP&A, accounting, treasury, audit |
| HR | Recruiting, employee relations, L&D, compensation |
| Marketing | Content, demand gen, brand, communications |
| Sales | Account management, sales ops, enablement |
| IT | Service desk, infrastructure, security, development |
| Legal | Contracts, compliance, litigation, IP |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding new agents.

## License

[MIT](LICENSE)
