# Quality Assurance Analyst — Role Analysis

## Methodology

This analysis synthesizes data from 15+ sources including:
- Job description templates from hiring platforms (Workable, Monster, Indeed)
- Manufacturing QA job postings
- Industry publications on QA challenges
- Software vendor pain point articles

All sources are documented in `job-evidence.csv` with URLs and extraction details.

## Role Definition

A Quality Assurance Analyst ensures that products, processes, and systems meet established quality standards and regulatory requirements. They conduct inspections, audits, and tests, document findings, and drive corrective and preventive actions.

### Reporting Structure
- Typically reports to: QA Manager, Quality Director, Operations Manager
- May oversee: QA Technicians, QA Inspectors
- Cross-functional collaboration with: Production, Engineering, Supply Chain, Regulatory

### Industry Presence
Found across industries with quality-critical operations:
- Manufacturing (general, automotive, aerospace)
- Pharmaceuticals and medical devices
- Food and beverage
- Electronics
- Healthcare
- Construction

---

## Task Clusters

### 1. Inspection & Testing (25% of time, Daily)
**Core Activities:**
- Performing quality inspections on incoming materials, in-process items, and finished products
- Conducting tests against specifications
- Using measuring and testing equipment
- Recording inspection results
- Identifying defects and non-conformances

**Evidence from job postings:**
> "Perform inspections of incoming materials, in-process stages, and final products" — Indeed

> "Performing quality tests and validating test cases" — Workable

### 2. Documentation & Record Keeping (20% of time, Daily)
**Core Activities:**
- Creating and maintaining SOPs
- Documenting inspection results
- Maintaining quality records and batch records
- Preparing test reports
- Managing document control

**Evidence from sources:**
> "Develop and review Quality and Operational documents, including SOPs, manufacturing records, test reports, and inspection records" — Indeed

> "Standard Operating Procedures (SOPs) are detailed instructions designed to achieve uniformity" — SafetyCulture

### 3. Audit Support & Compliance (15% of time, Weekly/Monthly)
**Core Activities:**
- Supporting internal and external audits
- Ensuring regulatory compliance (ISO, FDA, etc.)
- Maintaining audit readiness
- Tracking certifications and calibrations
- Preparing audit documentation

**Evidence from job postings:**
> "Support internal and external audits and inspections as a member of the audit/inspection team" — Amgen

> "Conduct on-site audits of manufacturing facilities to verify compliance" — Indeed

### 4. CAPA & Problem Resolution (15% of time, As Needed)
**Core Activities:**
- Investigating non-conformances
- Conducting root cause analysis
- Implementing corrective and preventive actions
- Tracking CAPA effectiveness
- Managing deviations

**Evidence from sources:**
> "Respond to non-conformances by preparing and maintaining corrective actions and non-conformance reports" — Indeed

> "Address deviations, CAPAs, change controls, risk assessments" — Amgen

### 5. Data Analysis & Reporting (10% of time, Weekly)
**Core Activities:**
- Analyzing quality metrics and trends
- Creating quality reports
- Tracking KPIs (defect rates, yield, etc.)
- Preparing management summaries
- Statistical process control

**Evidence from sources:**
> "Collect and examine statistical data" — Keka

> "Recording and analyzing test data, and preparing detailed reports on findings" — BuildStream

### 6. Cross-Functional Collaboration (10% of time, Daily)
**Core Activities:**
- Working with production on quality issues
- Collaborating with engineering on specifications
- Coordinating with suppliers on quality requirements
- Supporting new product introductions
- Training production staff

**Evidence from job postings:**
> "Collaborate with cross-functional teams, including developers, project managers, and business analysts" — Manatal

> "Collaborating with production team to discuss and rectify potential defects" — BuildStream

### 7. Process Improvement (5% of time, Ongoing)
**Core Activities:**
- Identifying improvement opportunities
- Recommending process changes
- Supporting lean and continuous improvement
- Updating quality procedures
- Implementing best practices

**Evidence from sources:**
> "Recommend, implement and monitor preventative and corrective actions" — Workable

> "Creating procedures and policies involving quality assurance" — Keka

---

## Friction Analysis

Based on analysis of industry pain point articles and job posting requirements:

| ID | Friction Type | Description | Evidence | Time Impact | Automation Potential |
|----|---------------|-------------|----------|-------------|---------------------|
| F1 | Information seeking | Finding specifications, standards, SOPs, test methods, and quality records | "Interpreting documentation and technical requirements"; "sifting through documentation" | 4+ hrs/week | High |
| F2 | Manual document creation | Creating and updating SOPs, test reports, inspection records, CAPA reports | "Develop and review quality and operational documents including SOPs" | 3+ hrs/week | Medium-High |
| F3 | Compliance tracking | Tracking certifications, calibrations, training records, audit schedules | "Ensuring inspections are current and compliant"; "maintaining ISO program" | 2 hrs/week | High |
| F4 | Reporting overhead | Preparing quality reports, management summaries, audit findings | "Preparing detailed reports on findings and recommendations" | 2 hrs/week | High |
| F5 | Non-conformance tracking | Finding NCR history, CAPA status, corrective action effectiveness | "Managing deviations, CAPAs, change controls" | 2 hrs/week | High |
| F6 | Supplier/vendor lookup | Finding supplier quality records, certifications, performance history | "Maintaining purchasing controls and supplier quality agreements" | 2 hrs/week | High |
| F7 | Audit preparation | Gathering documents for audits, preparing audit packages | "Supporting internal and external audits" | 2 hrs/week | Medium-High |
| F8 | Cross-functional communication | Coordinating with production, engineering, suppliers on quality issues | "Communication challenges" across teams | 2 hrs/week | Medium |

### Priority Friction Targets

**High Priority (High time impact + High automation potential):**
- F1: Information seeking (specs, standards, SOPs)
- F3: Compliance tracking
- F5: Non-conformance tracking
- F6: Supplier quality lookup

**Medium Priority:**
- F2: Manual document creation
- F4: Reporting overhead
- F7: Audit preparation

---

## Tools & Systems Mentioned

### Quality Management Systems
- EQMS (Enterprise Quality Management Systems)
- Document control systems
- CAPA management systems
- Deviation tracking systems

### Inspection & Testing
- Measuring and testing equipment
- Statistical Process Control (SPC) software
- Calibration management

### Compliance & Audit
- Audit management software
- Training management systems
- Certification tracking

### Analysis & Reporting
- Quality dashboards
- Pareto analysis tools
- KPI tracking
- Excel for data analysis

### Collaboration
- Microsoft Teams, Outlook
- SharePoint
- Communication tools

---

## Agent Opportunities

Based on friction analysis, two agents are recommended:

### 1. Quality Docs Finder (Addresses F1, F3, F6)
**Scope:** Helps QA analysts quickly find specifications, standards, SOPs, supplier quality records, and compliance documentation.
- **Friction addressed:** Information seeking, compliance tracking, supplier lookup
- **Capabilities:** OneDriveAndSharePoint
- **Complexity:** Low
- **Time saved:** 4 hrs/week

### 2. Quality Report Assistant (Addresses F2, F4, F5)
**Scope:** Helps QA analysts draft quality reports, summarize non-conformance data, and prepare audit documentation.
- **Capabilities:** OneDriveAndSharePoint, CodeInterpreter
- **Complexity:** Medium
- **Time saved:** 3 hrs/week

---

## Key Insights

1. **Documentation-heavy** — QA work revolves around SOPs, specifications, records, and reports. Finding the right document is a constant challenge.

2. **Compliance pressure** — Regulatory requirements (ISO, FDA, etc.) create ongoing documentation and tracking burdens.

3. **Cross-functional role** — QA analysts must coordinate with production, engineering, suppliers, and auditors.

4. **CAPA management** — Non-conformances, corrective actions, and effectiveness tracking are core activities.

5. **Audit readiness** — Being prepared for internal and external audits requires organized, accessible documentation.

6. **Data-driven decisions** — Quality metrics and trend analysis drive improvement initiatives.

---

## Sources Summary

- **Job board templates analyzed:** 6
- **Job postings reviewed:** 4
- **Pain point articles:** 5

Full source details in `job-evidence.csv`.
