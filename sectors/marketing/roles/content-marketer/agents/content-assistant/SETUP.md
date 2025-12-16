# Content Assistant - Setup Guide

## Overview

The Content Assistant helps Content Marketers draft content pieces more efficiently while maintaining brand voice and editorial standards. This agent creates outlines, briefs, social media posts, newsletter drafts, and performance summaries based on your organizational templates and guidelines.

**Deployment time:** ~45 minutes
**Technical requirements:** SharePoint libraries with brand guidelines, content templates, and reference materials

---

## Prerequisites

Before starting, ensure you have:

- [ ] Microsoft 365 Copilot license
- [ ] Access to create declarative agents (Copilot Studio or Teams Admin)
- [ ] SharePoint site(s) with brand and content documentation
- [ ] Documented brand voice guidelines
- [ ] Content templates (blog, brief, etc.)

---

## Step 1: Prepare Brand Guidelines

The agent's quality depends heavily on clear brand documentation. Ensure you have:

### Required Documents

**Brand Voice Guidelines** (Critical)
Your style guide should include:
- Brand personality description (3-5 adjectives)
- Voice characteristics (tone, style, approach)
- Do's and don'ts with examples
- Platform-specific voice guidance (social, blog, email)
- Terminology preferences and word choices to avoid

Example structure:
```
BrandGuidelines/
├── Brand Voice Guide.docx (REQUIRED)
├── Style Guide.docx (REQUIRED)
├── Messaging Framework.docx
├── Terminology Guide.docx
└── Platform Guidelines/
    ├── Social Media Voice.docx
    ├── Blog Writing Guidelines.docx
    └── Email Style Guide.docx
```

**Why this matters:** Without clear brand voice documentation, the agent will use generic approaches. The more specific your guidelines, the better the output.

---

## Step 2: Prepare Content Templates

Organize templates the agent can reference:

### Recommended Templates

```
ContentTemplates/
├── Blog/
│   ├── Blog Post Template.docx
│   ├── Blog Outline Template.docx
│   └── Blog Content Brief.docx
├── Social/
│   ├── LinkedIn Post Templates.docx
│   ├── Twitter Templates.docx
│   └── Social Media Calendar.xlsx
├── Email/
│   ├── Newsletter Template.docx
│   └── Email Sequence Template.docx
├── Reporting/
│   ├── Content Performance Report Template.xlsx
│   └── Monthly Summary Template.docx
└── Other/
    ├── Ebook Brief Template.docx
    └── Case Study Template.docx
```

### Template Best Practices

For optimal agent performance:
- Include example content in templates (not just blank fields)
- Add comments explaining each section's purpose
- Specify required vs. optional elements
- Include word count or length guidance
- Note formatting preferences

---

## Step 3: Set Up Reference Content (Optional but Recommended)

Having published content for reference helps the agent understand your style:

**Content Library** - Published examples
```
ContentLibrary/
├── Blog Posts/
│   └── [Top 10-20 blog posts that exemplify brand voice]
├── Newsletters/
│   └── [Recent newsletter examples]
└── Social/
    └── [High-performing social post examples]
```

**Performance Data** - For reporting capabilities
```
PerformanceData/
├── Monthly Reports/
├── Traffic Analytics/
└── Content Metrics.xlsx
```

---

## Step 4: Gather SharePoint URLs

Collect URLs for each library:

| Library | URL | Priority |
|---------|-----|----------|
| Brand Guidelines | `https://[tenant].sharepoint.com/sites/[site]/BrandGuidelines` | Required |
| Content Templates | `https://[tenant].sharepoint.com/sites/[site]/ContentTemplates` | Required |
| Content Library | `https://[tenant].sharepoint.com/sites/[site]/ContentLibrary` | Recommended |
| Performance Data | `https://[tenant].sharepoint.com/sites/[site]/PerformanceData` | Optional |

---

## Step 5: Configure the Manifest

1. Open `manifest-template.json`
2. Replace placeholder URLs:

```json
{
  "capabilities": [
    {
      "name": "OneDriveAndSharePoint",
      "items_by_url": [
        {
          "url": "https://contoso.sharepoint.com/sites/Marketing/BrandGuidelines"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/Marketing/ContentTemplates"
        },
        {
          "url": "https://contoso.sharepoint.com/sites/Marketing/ContentLibrary"
        }
      ]
    },
    {
      "name": "CodeInterpreter"
    }
  ]
}
```

3. Customize conversation starters for your common tasks
4. Save as `manifest.json`

---

## Step 6: Deploy the Agent

### Option A: Copilot Studio (Recommended)

1. Go to [Copilot Studio](https://copilotstudio.microsoft.com/)
2. Select **Create** → **New agent**
3. Choose **Configure with JSON**
4. Upload your configured `manifest.json`
5. Review the agent configuration
6. Click **Create**
7. Test thoroughly in the preview pane
8. When satisfied, click **Publish**

### Option B: Teams Admin Center

1. Go to [Teams Admin Center](https://admin.teams.microsoft.com/)
2. Navigate to **Copilot** → **Agents**
3. Select **+ Add agent**
4. Upload your `manifest.json`
5. Configure sharing settings
6. Deploy to selected users or groups

---

## Step 7: Test the Agent

### Quality Tests

Run these tests and evaluate output quality:

| Test | What to Evaluate |
|------|-----------------|
| "Create a blog outline about [topic you've written about before]" | Does the structure match your typical blogs? Is the voice correct? |
| "Write social media posts for a blog about [recent topic]" | Does the tone match your social voice? Are platform differences reflected? |
| "Draft a content brief for an ebook" | Does it follow your template structure? |
| "Create a monthly performance summary" | Is the format useful? Are the right metrics included? |

### Brand Voice Validation

Have your best writer or editor review agent outputs:
- Does it sound like your brand?
- Are there voice inconsistencies?
- What adjustments would they make?

Use feedback to improve your Brand Voice Guidelines document.

---

## Step 8: Share with Team

1. Configure appropriate sharing in Copilot Studio or Teams Admin
2. Create team introduction:
   - What the agent does (and doesn't do)
   - Example queries that work well
   - Reminder that ALL output is DRAFT requiring review
   - How to provide feedback on outputs

3. Recommended rollout:
   - Start with 2-3 power users for initial testing
   - Gather feedback for 1-2 weeks
   - Refine brand guidelines based on output quality
   - Roll out to full team

---

## Maintenance

### Weekly
- [ ] Review agent outputs for brand consistency
- [ ] Note any common adjustments users make

### Monthly  
- [ ] Update brand guidelines based on learnings
- [ ] Add new content examples to reference library
- [ ] Refresh templates if processes change
- [ ] Review conversation starters for relevance

### Quarterly
- [ ] Comprehensive brand voice audit
- [ ] Template refresh and optimization
- [ ] Review success metrics and adoption

---

## Troubleshooting

### Output doesn't match brand voice
1. Review your Brand Voice Guidelines document
2. Add more specific examples of do's and don'ts
3. Include more sample content in the Content Library
4. Be more explicit about tone and style preferences

### Agent invents information or statistics
- This should not happen with proper guardrails
- Verify the instructions are deployed correctly
- Check that the agent is using the DRAFT labeling
- Train users to always verify factual claims

### Templates aren't being followed
- Ensure templates are in the correct SharePoint library
- Check that templates have clear structure and labels
- Add more explicit instructions within templates

### Performance reports have wrong format
- Update the Performance Report Template with your preferred structure
- Add example reports to show the expected output
- Specify which metrics matter most to your organization

---

## Best Practices for Quality Output

### 1. Invest in Brand Documentation
The agent is only as good as your brand guidelines. Spending time on comprehensive documentation pays dividends.

### 2. Review and Iterate
Early outputs will reveal gaps in your guidelines. Use them as learning opportunities to improve documentation.

### 3. Set Expectations
Remind users that all output is DRAFT. The agent accelerates drafting; humans provide judgment and final approval.

### 4. Celebrate the Time Savings
Track how much faster teams can produce first drafts. This builds adoption and highlights ROI.

---

## Support

For issues with:
- **Agent configuration**: Contact your M365 admin
- **Output quality**: Review and enhance brand guidelines
- **Template issues**: Update templates in SharePoint
- **Strategic questions**: This agent drafts content, not strategy - consult your content lead

---

## Appendix: Sample Brand Voice Guide Structure

For optimal agent performance, include these sections in your Brand Voice Guidelines:

```markdown
# Brand Voice Guidelines

## Our Brand Personality
[3-5 adjectives that define your brand]

## Voice Characteristics

### We Sound Like...
- [Description with examples]

### We Don't Sound Like...
- [Description with examples]

## Writing Do's
- [Specific guidance with examples]

## Writing Don'ts
- [Specific guidance with examples]

## Tone by Context
- **Blog Posts**: [tone description]
- **Social Media**: [tone description]
- **Email**: [tone description]

## Words We Use
- [Preferred terminology]

## Words We Avoid
- [Terms to avoid and why]

## Examples of Our Voice
[Include 3-5 paragraphs showing ideal voice in action]
```
