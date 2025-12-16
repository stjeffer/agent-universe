# Content Finder - Setup Guide

## Overview

The Content Finder agent helps Content Marketers quickly locate existing content assets, brand guidelines, style documentation, and reference materials. This guide walks you through deploying the agent in your Microsoft 365 environment.

**Deployment time:** ~30 minutes
**Technical requirements:** SharePoint libraries with content assets and brand documentation

---

## Prerequisites

Before starting, ensure you have:

- [ ] Microsoft 365 Copilot license
- [ ] Access to create declarative agents (Copilot Studio or Teams Admin)
- [ ] SharePoint site(s) with content libraries
- [ ] Permissions to configure SharePoint access for Copilot

---

## Step 1: Prepare SharePoint Libraries

The agent requires access to organized content libraries. Set up or verify the following structure:

### Required Libraries

**1. Content Library** (Required)
```
ContentLibrary/
├── Blog Posts/
│   ├── 2024/
│   └── 2023/
├── Ebooks/
├── Guides/
├── Case Studies/
├── Webinars/
└── Newsletters/
```

**2. Brand Guidelines** (Required)
```
BrandGuidelines/
├── Style Guide.docx
├── Brand Voice Guidelines.docx
├── Visual Identity Standards.pdf
├── Messaging Framework.docx
├── Social Media Guidelines/
└── Terminology Guide.docx
```

### Recommended Libraries

**3. Content Templates** (Optional but recommended)
```
ContentTemplates/
├── Blog Post Template.docx
├── Content Brief Template.docx
├── Social Media Template.xlsx
├── Email Newsletter Template.docx
└── Case Study Template.docx
```

**4. Editorial Calendar** (Optional)
```
EditorialCalendar/
├── 2024 Content Calendar.xlsx
├── Topic Planning.docx
└── Publishing Schedule.xlsx
```

### Content Organization Best Practices

For optimal agent performance:
- Use consistent naming conventions (e.g., "YYYY-MM-DD Title.docx")
- Add metadata columns: Topic, Content Type, Status, Publish Date
- Include keywords in document titles and properties
- Keep the most current version of guidelines prominently named

---

## Step 2: Gather SharePoint URLs

Collect the full URLs for each library you want the agent to access:

1. Navigate to each library in SharePoint
2. Copy the URL from your browser
3. Record the URLs in this format:

| Library | URL |
|---------|-----|
| Content Library | `https://[tenant].sharepoint.com/sites/[site]/ContentLibrary` |
| Brand Guidelines | `https://[tenant].sharepoint.com/sites/[site]/BrandGuidelines` |
| Content Templates | `https://[tenant].sharepoint.com/sites/[site]/ContentTemplates` |
| Editorial Calendar | `https://[tenant].sharepoint.com/sites/[site]/EditorialCalendar` |

---

## Step 3: Configure the Manifest

1. Open `manifest-template.json`
2. Replace placeholder URLs with your actual SharePoint URLs:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        {
          "url": "https://contoso.sharepoint.com/sites/Marketing/ContentLibrary"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/Marketing/BrandGuidelines"
        }
      ]
    }
  ]
}
```

3. Customize conversation starters if desired
4. Save the file as `manifest.json`

---

## Step 4: Deploy the Agent

### Option A: Copilot Studio (Recommended)

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com/)
2. Select **Create** → **New agent**
3. Choose **Configure with JSON**
4. Upload your configured `manifest.json`
5. Review the agent configuration
6. Click **Create**
7. Test the agent in the preview pane
8. When satisfied, click **Publish**

### Option B: Teams Admin Center

1. Go to [Teams Admin Center](https://admin.teams.microsoft.com/)
2. Navigate to **Copilot** → **Agents**
3. Select **+ Add agent**
4. Upload your `manifest.json`
5. Configure sharing settings
6. Deploy to selected users or groups

---

## Step 5: Test the Agent

Verify the agent is working correctly with these test queries:

### Basic Functionality Tests

| Test | Expected Result |
|------|-----------------|
| "Find blog posts about [common topic]" | Returns relevant blog posts from Content Library |
| "What's our brand voice?" | Returns content from Brand Guidelines |
| "Where's the blog template?" | Returns template from Content Templates |
| "Show me our style guide" | Returns link to style guide document |

### Edge Case Tests

| Test | Expected Result |
|------|-----------------|
| "Find content about [topic we don't have]" | Agent acknowledges no results found |
| "Find blog posts from 2020" | Returns results or indicates old content |
| Request for confidential content | Agent respects permission boundaries |

---

## Step 6: Share with Users

1. In Copilot Studio or Teams Admin, configure sharing:
   - **Content Marketing team**: Full access
   - **Marketing department**: Viewer access
   - **Other departments**: Consider access based on need

2. Communicate rollout:
   - Send introduction email with example queries
   - Include conversation starters in onboarding
   - Share this README with users

---

## Maintenance

### Quarterly Tasks
- [ ] Review and update content library structure
- [ ] Verify brand guidelines are current
- [ ] Add new content templates as needed
- [ ] Check agent response quality with test queries

### As-Needed Tasks
- [ ] Add new SharePoint libraries when content structure changes
- [ ] Update manifest if conversation starters need refresh
- [ ] Review agent logs for common queries that aren't working

---

## Troubleshooting

### Agent can't find content that exists
- Verify SharePoint URL in manifest is correct
- Check that Copilot has permissions to the library
- Ensure content has appropriate metadata
- Wait for indexing (can take up to 24 hours for new content)

### Agent returns irrelevant results
- Review content organization and naming conventions
- Add more specific metadata to documents
- Consider more specific folder structures

### Users report inconsistent responses
- Verify brand guidelines document is current and complete
- Check for duplicate or conflicting documents
- Ensure "official" documents are clearly marked

---

## Support

For issues with:
- **Agent configuration**: Contact your M365 admin
- **SharePoint permissions**: Contact your SharePoint admin
- **Content organization**: Contact the Content Marketing lead

---

## Appendix: Recommended Metadata Schema

For optimal search performance, consider adding these metadata columns to your SharePoint libraries:

| Column | Type | Purpose |
|--------|------|---------|
| Content Type | Choice | Blog, Ebook, Guide, Case Study, etc. |
| Topic | Managed Metadata | Content topic/category |
| Publish Date | Date | When content was published |
| Status | Choice | Draft, Published, Archived |
| Target Persona | Choice | Which audience segment |
| Primary Keyword | Text | Main SEO keyword |
| Performance | Choice | High, Medium, Low performing |
