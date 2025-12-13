# Contributing to Agent Universe

Thank you for your interest in contributing to the Agent Universe catalog!

## How to contribute

### Adding a new agent

1. **Choose or create the role**
   - Check if the role already exists in `sectors/{sector}/roles/`
   - If not, create the role folder and `_role.json` with friction analysis

2. **Create the agent folder**
   ```
   sectors/{sector}/roles/{role}/agents/{agent-name}/
   ```

3. **Create required files**
   - `blueprint.json` — Structured agent definition (see schema)
   - `instructions.md` — Human-readable instructions for the agent
   - `manifest-template.json` — M365 manifest with placeholders
   - `SETUP.md` — Deployment guide
   - `README.md` — Quick overview

4. **Update the catalog**
   - Add entry to `catalog.json`
   - Update indexes

5. **Submit a pull request**
   - Describe the role and friction addressed
   - Include any testing notes

### Improving an existing agent

1. Fork the repository
2. Make your changes
3. Update the version in `blueprint.json`
4. Submit a pull request with description of changes

## Standards

### Naming conventions

- **Folder names**: kebab-case (e.g., `contract-supplier-finder`)
- **Agent IDs**: kebab-case, unique within the role
- **File names**: As specified in structure

### Instructions quality

Good instructions should:
- Clearly define the agent's role and scope
- Include specific guardrails (what NOT to do)
- Provide examples of good interactions
- Handle edge cases gracefully
- Be under 8,000 characters (M365 limit)

### Friction analysis

When adding a new role, include:
- Analysis based on real job descriptions (cite sources)
- Quantified time estimates where possible
- Clear mapping from friction to agent opportunities

## Review criteria

Pull requests will be reviewed for:

- [ ] Blueprint follows schema
- [ ] Instructions are clear and complete
- [ ] Setup guide is accurate and actionable
- [ ] RAI compliance (no harmful content)
- [ ] Catalog entry is correct
- [ ] Documentation is complete

## Questions?

Open an issue for questions about contributing.
