# Launch Content Assistant - Setup Guide

## Prerequisites

Before deploying this agent, ensure you have:

- [ ] Microsoft 365 Copilot license
- [ ] Access to Copilot Studio or declarative agent deployment tools
- [ ] SharePoint site with PMM content and templates
- [ ] Established positioning and messaging frameworks
- [ ] Appropriate permissions to create/deploy agents

## Step 1: Prepare SharePoint Content

### Required Libraries

Create or identify the following SharePoint libraries:

#### 1. Positioning & Messaging Library
**Purpose**: Store approved positioning frameworks, messaging guides, and value propositions

**Recommended Structure**:
```
/Positioning-Messaging/
├── Frameworks/
│   ├── Company-Positioning-Framework.docx
│   ├── Product-A-Positioning.docx
│   └── Product-B-Positioning.docx
├── Messaging-Guides/
│   ├── Enterprise-Messaging-Guide.docx
│   ├── SMB-Messaging-Guide.docx
│   └── Vertical-Messaging/
│       ├── Healthcare-Messaging.docx
│       └── Financial-Services-Messaging.docx
├── Value-Propositions/
│   └── Value-Prop-Library.docx
└── Brand-Voice/
    └── Tone-and-Voice-Guidelines.docx
```

**Critical Documents to Include**:
- Master positioning framework
- Persona-specific messaging guides
- Approved value proposition statements
- Brand voice and tone guidelines

#### 2. Launch Templates Library
**Purpose**: Store standard templates for launch communications

**Recommended Structure**:
```
/Launch-Templates/
├── Announcements/
│   ├── Internal-Launch-Announcement-Template.docx
│   ├── Customer-Announcement-Template.docx
│   └── Partner-Announcement-Template.docx
├── Sales-Enablement/
│   ├── Feature-Talking-Points-Template.docx
│   ├── Battlecard-Template.docx
│   └── Email-Templates/
│       ├── Launch-Email-to-Sales.docx
│       └── Feature-Update-Email.docx
├── Competitive/
│   ├── Competitive-Comparison-Table-Template.xlsx
│   └── Win-Loss-Summary-Template.docx
└── Checklists/
    ├── Launch-Checklist-Major.docx
    └── Launch-Checklist-Minor.docx
```

#### 3. Product Documentation Library
**Purpose**: Store feature specs, release notes, and product information

**Recommended Structure**:
```
/Product-Documentation/
├── Feature-Specs/
│   ├── Feature-A-Spec-v2.1.docx
│   ├── Feature-B-Spec-v1.0.docx
│   └── ...
├── Release-Notes/
│   ├── 2024/
│   │   ├── Release-2024-Q4.docx
│   │   └── ...
│   └── Archive/
├── Product-Overview/
│   ├── Product-A-Overview.docx
│   └── Product-B-Overview.docx
└── Technical-Docs/
    └── Integration-Guide.docx
```

#### 4. Competitive Battlecards Library (Optional but Recommended)
**Purpose**: Reference for competitive updates and messaging

*See Competitive Intel Finder setup for recommended structure*

## Step 2: Create Essential Documents

If you don't have these documents, create them before deploying the agent:

### Minimum Viable Content

1. **Positioning Framework** - At minimum, document:
   - Target audience definitions
   - Key value propositions (3-5)
   - Competitive differentiation points
   - Approved taglines/headlines

2. **Launch Announcement Template** - Include:
   - Standard structure/sections
   - Required information fields
   - Example completed announcement

3. **Talking Points Template** - Include:
   - 30-second pitch format
   - Persona-specific sections
   - Objection handling structure

## Step 3: Gather SharePoint URLs

For each library, get the full URL:

```
https://contoso.sharepoint.com/sites/ProductMarketing/Positioning-Messaging
https://contoso.sharepoint.com/sites/ProductMarketing/Launch-Templates
https://contoso.sharepoint.com/sites/ProductMarketing/Product-Documentation
https://contoso.sharepoint.com/sites/ProductMarketing/Competitive-Battlecards
```

## Step 4: Configure the Manifest

1. Open `manifest-template.json`

2. Replace the placeholder URLs:

| Placeholder | Replace With |
|-------------|--------------|
| `{{POSITIONING_MESSAGING_URL}}` | Your Positioning & Messaging library URL |
| `{{LAUNCH_TEMPLATES_URL}}` | Your Launch Templates library URL |
| `{{PRODUCT_DOCUMENTATION_URL}}` | Your Product Documentation library URL |
| `{{COMPETITIVE_BATTLECARDS_URL}}` | Your Competitive Battlecards library URL |

3. Save as `manifest.json`

## Step 5: Deploy the Agent

### Option A: Copilot Studio (Recommended)

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com)
2. Create a new Declarative Agent
3. Upload your configured `manifest.json`
4. Upload `instructions.md` to the same location
5. Test the agent in the preview pane
6. Publish when ready

### Option B: Teams Admin Center

1. Package the agent files into a Teams app package
2. Upload via Teams Admin Center
3. Assign to appropriate users/groups

## Step 6: Test the Agent

Run these test queries to verify setup:

### Template Access Test
```
"Show me the launch announcement template"
```
Expected: Agent should reference or describe the template structure

### Positioning Usage Test
```
"Draft a value proposition statement for [your product]"
```
Expected: Agent should pull from positioning framework, not invent new messaging

### Drafting Test
```
"Draft an internal launch announcement for [recent feature]"
```
Expected: Agent should produce structured draft using template format and positioning

### Source Citation Test
```
"Create talking points for [feature]"
```
Expected: Agent should cite source documents used in the response

### Boundary Test
```
"Write a press release for [product]"
```
Expected: Agent should draft but clearly note review requirements

## Step 7: User Onboarding

Share these materials with PMM team:
- Agent name and access method
- Example queries and use cases
- Process for reviewing and approving drafted content
- How to provide feedback on drafts
- Reminder that all output is DRAFT requiring review

### Recommended Workflow

1. **Request**: Ask agent to draft content
2. **Review**: PMM reviews draft for accuracy and alignment
3. **Edit**: Make necessary changes in your preferred editor
4. **Approve**: Get required sign-offs (legal, comms, etc.)
5. **Publish**: Distribute through normal channels

## Maintenance

### Weekly
- Review agent usage patterns
- Note drafts that required significant revision (improve source docs)

### Monthly
- Update positioning documents with any approved messaging changes
- Add new feature specs as they're created
- Refresh templates based on what's working

### Quarterly
- Review and update positioning framework
- Archive outdated templates
- Evaluate agent effectiveness with PMM team

### After Major Launches
- Add launch communications as examples for future reference
- Update competitive battlecards with launch learnings
- Document any new messaging that was approved

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Drafts don't match brand voice | Check Brand Voice doc is in library; update guidelines |
| Agent invents features | Verify Product Documentation is accessible and current |
| Templates not being used | Confirm template library URL is correct |
| Generic/weak messaging | Strengthen positioning framework with specific differentiators |
| Missing competitive context | Ensure Battlecards library is connected |

## Content Quality Tips

For best agent output, ensure source documents have:

1. **Clear structure** - Use headers, bullet points, tables
2. **Specific examples** - Include sample statements, not just frameworks
3. **Approval status** - Mark documents as "Approved" vs "Draft"
4. **Current dates** - Update "Last reviewed" dates regularly
5. **Persona labels** - Tag content by target audience when applicable

## Support

For issues with this agent:
1. Check SharePoint library content quality
2. Review agent logs in Copilot Studio
3. Compare poor outputs to source documents
4. Contact your M365 admin for deployment issues
