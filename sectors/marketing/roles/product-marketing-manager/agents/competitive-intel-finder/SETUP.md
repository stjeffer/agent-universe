# Competitive Intel Finder - Setup Guide

## Prerequisites

Before deploying this agent, ensure you have:

- [ ] Microsoft 365 Copilot license
- [ ] Access to Copilot Studio or declarative agent deployment tools
- [ ] SharePoint site with competitive intelligence content
- [ ] Appropriate permissions to create/deploy agents

## Step 1: Prepare SharePoint Content

### Required Libraries

Create or identify the following SharePoint libraries:

#### 1. Competitive Battlecards Library
**Purpose**: Store competitor-specific battlecards and comparison documents

**Recommended Structure**:
```
/Competitive-Battlecards/
├── Competitor-A/
│   ├── Competitor-A-Battlecard.docx
│   ├── Competitor-A-Pricing.xlsx
│   └── Competitor-A-Feature-Comparison.docx
├── Competitor-B/
│   └── ...
└── Templates/
    └── Battlecard-Template.docx
```

**Metadata Columns** (recommended):
- Competitor Name (Choice)
- Last Updated (Date)
- Owner (Person)
- Confidence Level (Choice: High/Medium/Low)

#### 2. Win/Loss Analysis Library
**Purpose**: Store win/loss reports and competitive deal outcomes

**Recommended Structure**:
```
/Win-Loss-Analysis/
├── 2024/
│   ├── Q4/
│   │   ├── Q4-2024-Win-Loss-Summary.docx
│   │   └── Deal-Analysis/
│   ├── Q3/
│   └── ...
├── By-Competitor/
│   ├── Competitor-A-Win-Loss.xlsx
│   └── ...
└── By-Vertical/
    ├── Healthcare-Win-Loss.xlsx
    └── ...
```

#### 3. Market Research Library (Optional)
**Purpose**: Store analyst reports, market studies, and industry research

**Recommended Structure**:
```
/Market-Research/
├── Analyst-Reports/
│   ├── Gartner/
│   ├── Forrester/
│   └── IDC/
├── Industry-Studies/
└── Internal-Research/
```

#### 4. PMM Knowledge Base
**Purpose**: Central repository for positioning docs and messaging frameworks

**Recommended Structure**:
```
/PMM-Knowledge-Base/
├── Positioning/
│   ├── Product-Positioning-Framework.docx
│   └── Value-Propositions.docx
├── Messaging/
│   ├── Messaging-Guide.docx
│   └── Talk-Tracks/
├── Personas/
└── Competitive/
    └── Competitive-Overview.docx
```

## Step 2: Gather SharePoint URLs

For each library, get the full URL. Navigate to the library in SharePoint and copy the URL from your browser.

Example URLs:
```
https://contoso.sharepoint.com/sites/ProductMarketing/Competitive-Battlecards
https://contoso.sharepoint.com/sites/ProductMarketing/Win-Loss-Analysis
https://contoso.sharepoint.com/sites/ProductMarketing/Market-Research
https://contoso.sharepoint.com/sites/ProductMarketing/PMM-Knowledge-Base
```

## Step 3: Configure the Manifest

1. Open `manifest-template.json`

2. Replace the placeholder URLs:

| Placeholder | Replace With |
|-------------|--------------|
| `{{BATTLECARDS_LIBRARY_URL}}` | Your Competitive Battlecards library URL |
| `{{WINLOSS_LIBRARY_URL}}` | Your Win/Loss Analysis library URL |
| `{{MARKET_RESEARCH_LIBRARY_URL}}` | Your Market Research library URL |
| `{{PMM_KNOWLEDGE_BASE_URL}}` | Your PMM Knowledge Base URL |

3. Save as `manifest.json`

## Step 4: Deploy the Agent

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

## Step 5: Test the Agent

Run these test queries to verify setup:

### Basic Retrieval Test
```
"What competitors do we have battlecards for?"
```
Expected: Agent should list competitors from your Battlecards library

### Specific Competitor Test
```
"What are our differentiators against [your top competitor]?"
```
Expected: Agent should return information from the relevant battlecard

### Win/Loss Test
```
"Show me recent win/loss data"
```
Expected: Agent should surface information from Win/Loss library

### Cross-Repository Test
```
"Find all information we have about [competitor] including win rates"
```
Expected: Agent should pull from both Battlecards and Win/Loss repositories

## Step 6: User Onboarding

Share these materials with PMM team:
- Agent name and how to access it in Copilot
- Example queries (see conversation starters in manifest)
- Process for reporting issues or requesting improvements
- Guidelines for keeping source content updated

## Maintenance

### Weekly
- Review agent usage patterns in Copilot analytics
- Note any common queries that return poor results

### Monthly
- Audit battlecard freshness (flag documents >90 days old)
- Update win/loss data after quarterly analysis complete
- Add new competitors as they become relevant

### Quarterly
- Review and update agent instructions based on user feedback
- Evaluate if additional data sources should be added
- Check for new SharePoint content that should be included

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Agent can't find documents | Verify SharePoint URLs are correct and accessible |
| Results are outdated | Check document metadata; update source content |
| Agent returns irrelevant results | Review instructions.md; add more specific guardrails |
| Users report missing competitors | Add competitor battlecard to library; no agent changes needed |
| Permission errors | Ensure agent has read access to all SharePoint libraries |

## Support

For issues with this agent:
1. Check SharePoint library access and content
2. Review agent logs in Copilot Studio
3. Contact your M365 admin for deployment issues
