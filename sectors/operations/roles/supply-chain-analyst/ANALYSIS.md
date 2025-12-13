# Supply Chain Analyst — Role Analysis

## Methodology

This analysis synthesizes data from 40+ sources including:
- Job description templates from major hiring platforms (Indeed, Workable, Glassdoor, LinkedIn)
- Active job postings across multiple job boards
- Industry publications on supply chain pain points
- Career resources and resume guides
- ERP vendor documentation

All sources are documented in `job-evidence.csv` with URLs and extraction details.

## Role Definition

A Supply Chain Analyst collects, analyzes, and interprets data to optimize supply chain operations. They work across procurement, inventory management, logistics, and demand planning to identify inefficiencies, reduce costs, and improve delivery performance.

### Reporting Structure
- Typically reports to: Supply Chain Manager, Operations Manager, or Director of Supply Chain
- May work within: Operations, Logistics, Procurement, or Planning departments
- Cross-functional collaboration with: Finance, Sales, Production, Warehousing, IT

### Industry Presence
Found across virtually all industries with significant presence in:
- Manufacturing
- Retail & E-commerce
- Consumer Packaged Goods (CPG)
- Healthcare & Pharmaceuticals
- Technology
- Food & Beverage
- Government

---

## Task Clusters

### 1. Data Collection & Validation (20% of time, Daily)
**Core Activities:**
- Gathering data from ERP systems (SAP, Oracle, NetSuite)
- Validating data accuracy across multiple sources
- Cleaning and standardizing datasets
- Maintaining data in spreadsheets and databases
- Reconciling discrepancies between systems

**Evidence from job postings:**
> "Gather, clean, and validate supply chain data from multiple sources (ERP systems, spreadsheets, databases)" — Indeed Oracle ERP Jobs

> "Organize documentation and update ERP system records" — 4 Corner Resources

### 2. Reporting & Dashboard Development (20% of time, Daily/Weekly)
**Core Activities:**
- Building and maintaining KPI dashboards (Power BI, Tableau)
- Creating periodic reports for management
- Visualizing supply chain metrics
- Tracking performance against targets
- Presenting findings to stakeholders

**Evidence from job postings:**
> "Design, build, and maintain Power BI dashboards and reports to visualize KPIs and operational metrics" — Indeed

> "Developed KPI dashboard improving visibility into supply chain metrics by 50%" — CV Compiler Resume Examples

### 3. Demand Planning & Forecasting (15% of time, Weekly)
**Core Activities:**
- Analyzing historical data for demand patterns
- Developing and maintaining forecasting models
- Collaborating with Sales on demand signals
- Adjusting forecasts for seasonality, promotions
- Supporting S&OP (Sales & Operations Planning) processes

**Evidence from job postings:**
> "Accurate demand forecasts, and development of clear and accessible tools/processes for analysis" — Indeed Data Analyst Jobs

> "Developing forecasting models to predict supply and demand trends" — Teal Career Paths

### 4. Inventory Analysis & Optimization (15% of time, Daily/Weekly)
**Core Activities:**
- Monitoring inventory levels and turns
- Analyzing safety stock requirements
- Identifying slow-moving or excess inventory
- Recommending reorder points
- Supporting inventory reduction initiatives

**Evidence from job postings:**
> "Analyze inventory trends and generate reports to drive decision-making" — CoreWeave job posting

> "Track and manage inventory levels and reorder supplies as needed" — Indeed NYC Jobs

### 5. Supplier & Vendor Performance Analysis (10% of time, Weekly/Monthly)
**Core Activities:**
- Tracking supplier delivery performance
- Analyzing vendor pricing and costs
- Comparing supplier metrics
- Supporting vendor selection decisions
- Identifying supply risks

**Evidence from job postings:**
> "Evaluate vendor performance and recommend improvements or alternatives" — 4 Corner Resources

> "Research partner companies and seek to negotiate best-price contracts" — Glassdoor Template

### 6. Process Improvement & Optimization (10% of time, Ongoing)
**Core Activities:**
- Identifying bottlenecks and inefficiencies
- Recommending process improvements
- Supporting automation initiatives
- Conducting root cause analysis
- Implementing Lean/Six Sigma methodologies

**Evidence from job postings:**
> "Identify bottlenecks and suggest solutions for process improvements" — Teal Career Paths

> "Implement process improvements within the supply chain to enhance efficiency and reduce costs" — Indeed Data Analyst Jobs

### 7. Cross-Functional Collaboration (5% of time, Daily)
**Core Activities:**
- Coordinating with Production, Sales, Finance
- Participating in planning meetings
- Communicating supply chain status
- Aligning on priorities and constraints

**Evidence from job postings:**
> "Collaborating with cross-functional teams to implement supply chain strategies" — Teal Career Paths

> "Work with cross-functional teams to ensure alignment on inventory levels, demand forecasts, and supply chain strategies" — Indeed Manhattan Jobs

### 8. System Support & Enhancement (5% of time, As Needed)
**Core Activities:**
- Supporting ERP implementations and upgrades
- Testing system changes
- Documenting processes
- Training users on tools and reports

**Evidence from job postings:**
> "Assist with ERP system implementation or enhancements" — 4 Corner Resources

> "Collaborate with IT and business stakeholders to enhance ERP or reporting tools" — 4 Corner Resources

---

## Friction Analysis

Based on analysis of industry pain point articles and job posting requirements:

| ID | Friction Type | Description | Evidence | Time Impact | Automation Potential |
|----|---------------|-------------|----------|-------------|---------------------|
| F1 | Data gathering & validation | Collecting data from multiple ERP systems, spreadsheets, databases and ensuring accuracy | "Gather, clean, and validate supply chain data from multiple sources" | 5+ hrs/week | High |
| F2 | Manual reporting | Creating periodic reports manually, copying data between systems | "Automated data collection and reporting processes, saving 150 hours per month" | 4+ hrs/week | High |
| F3 | Dashboard maintenance | Keeping dashboards updated, fixing data issues, responding to ad-hoc requests | "Build and maintain dashboards and reports to monitor supply chain health" | 3 hrs/week | Medium-High |
| F4 | Inventory status tracking | Monitoring inventory levels across locations, identifying exceptions | "Track and manage inventory levels"; "Lack of real-time visibility into supply chain" | 3 hrs/week | High |
| F5 | Supplier information lookup | Finding supplier performance data, pricing history, contact information | "Research partner companies"; "evaluate vendor performance" | 2 hrs/week | High |
| F6 | Forecasting analysis | Running forecasting models, analyzing accuracy, adjusting parameters | "Develop forecasting models to predict supply and demand trends" | 3 hrs/week | Medium |
| F7 | Exception identification | Finding and investigating anomalies, stockouts, delivery delays | "Identify problematic areas"; "Reactive management of likely impacts" | 2 hrs/week | Medium-High |
| F8 | Cross-system reconciliation | Comparing data across ERP, WMS, TMS to find discrepancies | "Interpreting data flows that span across order management, inventory tracking, logistics" | 2 hrs/week | Medium |

### Priority Friction Targets

**High Priority (High time impact + High automation potential):**
- F1: Data gathering & validation
- F2: Manual reporting
- F4: Inventory status tracking

**Medium Priority:**
- F3: Dashboard maintenance
- F5: Supplier information lookup
- F7: Exception identification

---

## Tools & Systems Mentioned

### ERP Systems (most frequently cited)
- SAP (S/4HANA, MM, SCM)
- Oracle (SCM Cloud, Fusion)
- NetSuite
- Microsoft Dynamics 365
- JDE/JD Edwards
- Infor

### Analytics & BI Tools
- Microsoft Power BI
- Tableau
- Excel (Advanced: pivot tables, VLOOKUP, macros, VBA)
- SQL
- Python
- R

### Specialized Supply Chain Tools
- Kinaxis RapidResponse
- JDA/Blue Yonder
- Anaplan
- Manhattan Associates
- E2open

### Collaboration
- Microsoft Teams
- Outlook/Email

---

## Agent Opportunities

Based on friction analysis, three agents are recommended:

### 1. Inventory & Order Tracker (Addresses F1, F4, F7)
**Scope:** Helps analysts quickly find inventory status, order information, and supply chain exceptions across documentation.
- **Friction addressed:** Data gathering, inventory tracking, exception identification
- **Capabilities:** OneDriveAndSharePoint, GraphConnectors (optional for ERP)
- **Complexity:** Low
- **Time saved:** 4 hrs/week

### 2. Supply Chain Report Assistant (Addresses F2, F3)
**Scope:** Helps analysts draft periodic reports, summarize KPIs, and create management updates from supply chain data.
- **Capabilities:** OneDriveAndSharePoint, CodeInterpreter
- **Complexity:** Medium
- **Time saved:** 3 hrs/week

### 3. Supplier Risk Monitor (Addresses F5, F8)
**Scope:** Helps analysts find supplier performance data, identify risks, and compare vendor metrics.
- **Capabilities:** OneDriveAndSharePoint, WebSearch (for external risk signals)
- **Complexity:** Medium
- **Time saved:** 2 hrs/week

---

## Key Insights

1. **Data is central to the role** — Nearly every responsibility involves collecting, validating, analyzing, or reporting on data. Agents that accelerate data access will have highest impact.

2. **Multi-system complexity** — Supply chain analysts routinely work across 3-5+ systems (ERP, WMS, TMS, BI tools, spreadsheets). Reducing context-switching is a major opportunity.

3. **Manual reporting is a major time sink** — Multiple sources cite hours spent on repetitive reporting tasks that could be automated or assisted.

4. **Visibility is the #1 pain point** — Industry articles consistently cite "lack of visibility" as the top supply chain challenge. Agents that improve information findability address this directly.

5. **Cross-functional coordination required** — The role requires working with many departments, making clear communication and documentation important.

---

## Sources Summary

- **Job board templates analyzed:** 8
- **Active job listings reviewed:** 12+
- **Industry pain point articles:** 10
- **Career/resume resources:** 4
- **Vendor documentation:** 2

Full source details in `job-evidence.csv`.
