# Vendor Research Brief — Document Template Structure

This defines the sections, order, and content expectations for the Vendor Research Brief .docx output. The coordinator uses this to generate the final document after all agent research is complete.

## Document Structure

### Cover Page
- "VENDOR RESEARCH BRIEF" subtitle
- Vendor name (large, bold, brand color)
- Product category subtitle
- Institution name and department
- Date
- "CONFIDENTIAL" footer

### Executive Summary (1 page)
- 2-3 paragraph overview of the vendor and findings
- **At-a-Glance Table** (2-column: Category, Summary)
  - Company: founding, valuation, employees, investors
  - Product: one-sentence description of capabilities
  - Certifications: list key certifications
  - Ratings: G2, Capterra, Gartner Peer Insights scores
  - Pricing: model and estimated cost range with edu discount
  - Higher Ed Fit: case study count, EDUCAUSE presence
  - Build Feasibility: verdict (BUILD VIABLE / BUILD WITH CAVEATS / LEAN TOWARD BUY / STRONGLY FAVOR BUY) and one-sentence rationale

### Readiness Scorecard (1 page)
Color-coded table mapping vendor against institutional procurement requirements.

| Requirement | Status | Risk | Notes |
|---|---|---|---|
| HECVAT Assessment | | | |
| SOC 2 Type II | | | |
| FERPA Compliance | | | |
| GLBA Compliance | | | |
| SAML 2.0 / SSO | | | |
| MFA / Duo | | | |
| Data in US Only | | | |
| Accessibility (WCAG 2.0 AA) | | | |
| REST API / Integrations | | | |
| SLA / Uptime Guarantee | | | |
| Liability Cap Adequate | | | |
| Breach Notification | | | |
| Price Escalation Cap | | | |
| Build Feasibility | | | |

**Status color coding:**
- Green (#2E7D32): CERTIFIED, SUPPORTED, YES, STRONGLY FAVOR BUY
- Amber (#E65100): PARTIAL, UNCLEAR, NEGOTIABLE, LEAN TOWARD BUY, BUILD WITH CAVEATS
- Red (#D42121): NOT FOUND, CONCERNING, NOT PUBLIC, BUILD VIABLE (red because it signals the vendor may be replaceable — a risk to the procurement case)

### Section 1: Security Review
From Agent 1 findings. Subsections:
- 1.1 Certifications (detailed table)
- 1.2 HECVAT Assessment (status, version logic, action required)
- 1.3 Data Classification Assessment
- 1.4 Access Controls (SSO, MFA, RBAC, audit logging)
- 1.5 Data Encryption & Storage (at rest, in transit, residency)
- 1.6 AI/ML Disclosure (if applicable)
- 1.7 Vulnerability History (CVEs, incidents, bug bounty)
- 1.8 Technical Integration & Data Flow
- 1.9 Institutional Security Assessment (gaps, mitigations)

### Section 2: Market Reputation
From Agent 2 findings. Subsections:
- 2.1 Analyst Recognition (Gartner, Forrester, IDC)
- 2.2 Review Platform Ratings (table: platform, score, reviews)
- 2.3 Company Financials (founding, funding, valuation, revenue)
- 2.4 Customer Concerns (themed criticisms from reviews/forums)

### Section 3: Cost Analysis
From Agent 3 findings. Subsections:
- 3.1 Pricing Model (per-device/user/tech, tiers, billing)
- 3.2 Estimated Pricing Table (scale vs. cost, with edu discount column)
- 3.3 Included vs. Add-Ons (feature/cost table)
- 3.4 Competitive Cost Comparison (table: vendor, price, model, features)
- 3.5 ROI Evidence (quantified savings)
- 3.6 Budget Considerations (institutional-specific)

### Section 4: Legal & Contract Management
From Agent 4 findings. Subsections:
- 4.1 Data Processing Agreement (key terms)
- 4.2 FERPA and GLBA (compliance status, action required)
- 4.3 Contract Gap Analysis (table: requirement, vendor status, action needed)
- 4.4 Sub-processors (list, notification provisions)
- 4.5 Exit Strategy (data return, deletion, grace period)

### Section 5: Competitive Landscape
From Agent 5 findings. Subsections:
- 5.1 Feature Comparison Matrix (multi-column table)
- 5.2 Institutional Context (current tools, consolidation opportunity)
- 5.3 Integration with Institutional Ecosystem (detailed compatibility)

### Section 6: Higher Education Fit
From Agent 6 findings. Subsections:
- 6.1 Case Studies (table: institution, type, size, scope, outcome)
- 6.2 EDUCAUSE Visibility
- 6.3 Gaps for Higher Ed (bulleted list with context)

### Section 7: Build Feasibility Assessment
From Agent 7 findings. Subsections:
- 7.1 Verdict & Executive Assessment (BUILD VIABLE / BUILD WITH CAVEATS / LEAN TOWARD BUY / STRONGLY FAVOR BUY with 2-3 sentence rationale)
- 7.2 Decision Matrix (table: Factor, Assessment, Impact on Decision)
  - Application Complexity (Low/Medium/High/Very High → Favors Build/Neutral/Favors Buy)
  - Data Sensitivity (Public/Internal/Restricted/Confidential → Favors Build/Neutral/Favors Buy)
  - Architecture Requirements (Simple/Moderate/Complex/Enterprise → Favors Build/Neutral/Favors Buy)
  - AI Development Feasibility (High/Medium/Low → Favors Build/Neutral/Favors Buy)
  - Maintenance Burden (Low/Medium/High → Favors Build/Neutral/Favors Buy)
  - 3-Year TCO Comparison (Build Cheaper/Comparable/Buy Cheaper → Favors Build/Neutral/Favors Buy)
  - Risk Profile (Build Lower Risk/Comparable/Buy Lower Risk → Favors Build/Neutral/Favors Buy)
- 7.3 Application Complexity Analysis (feature decomposition, MVP scope)
- 7.4 Architecture Estimate (frontend, backend, database, infrastructure, integrations)
- 7.5 Open-Source Alternatives (table: name, GitHub stars, license, feature coverage, hosting requirements)
- 7.6 TCO Comparison (3-year and 5-year table: Buy vs. Build with line items)
- 7.7 Risk Comparison (side-by-side: buy risks vs. build risks)

### Section 8: Recommendations & Next Steps
Synthesized from all agents. Subsections:
- 8.1 Pre-Engagement Requirements (numbered list of must-dos)
- 8.2 Contract Negotiation Priorities (ranked, with addendum section references)
- 8.3 Technical Evaluation (POC scope, integration tests, accessibility audit)
- 8.4 Build Feasibility Follow-Up (if applicable: OSS pilots, architecture spikes, prototype sprints, or "no further evaluation recommended" with rationale)
- 8.5 Analyst Consultation (if institution has Gartner/Forrester access)

### Section 9: Key Sources
Organized by category:
- Vendor Official (URLs)
- Industry Analysts (reports)
- Review Platforms (URLs)
- Higher Education (EDUCAUSE, case studies)
- Open-Source Alternatives (GitHub repositories, project sites)
- Institutional Internal (addendum, guidelines, security assessment)

## Formatting Guidelines

- Use institutional brand colors if known, otherwise use a professional blue/gray palette
- Tables should use color-coded status cells for the Readiness Scorecard (green/amber/red with white text)
- The Build Feasibility verdict should use the same color coding: green = STRONGLY FAVOR BUY, amber = LEAN TOWARD BUY or BUILD WITH CAVEATS, red = BUILD VIABLE
- Page headers: "[Vendor Name] Vendor Research Brief"
- Page footers: "[Institution] • [Department] • Page [N]"
- US Letter size (8.5" x 11"), 1" margins
- Professional serif font for headings, sans-serif for body text
