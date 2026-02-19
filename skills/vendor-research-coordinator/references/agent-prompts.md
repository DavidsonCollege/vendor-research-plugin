# Agent Prompt Templates

These are the full prompt templates for each of the 7 research agents launched by the coordinator. When launching agents via the Task tool, customize these templates by replacing `[VENDOR]` with the actual vendor name and adding any institution-specific context.

---

## Security Review

```
Research [VENDOR] from a cybersecurity and information security perspective. This is for a higher education institution evaluating the product for purchase. The institution has regulatory obligations under FERPA, GLBA, HIPAA, PCI-DSS, and GDPR.

Investigate and report on:

1. HECVAT Assessment — Search EDUCAUSE repositories, REN-ISAC Cloud Broker Index, and the vendor's documentation for any completed HECVAT (Version 4.x preferred). Full Version is required if the software processes payments or handles Confidential data (SSNs, health records, financial account numbers). Lite Version is acceptable only if no payments and data is Internal or Public. Must be updated within last 18 months.

2. Security Certifications — SOC 2 Type II, ISO 27001, FedRAMP, HIPAA, GDPR, CCPA, NIST 800-171, CSA STAR. Get specifics: auditor names, dates, scope, and how to access reports.

3. Data Classification — Determine what data the vendor handles and classify it as Public, Internal, Restricted, or Confidential per higher ed data security policy. If Confidential, list every data element.

4. Access Controls — SSO/SAML support (Azure AD, Okta, Shibboleth), native MFA options, RBAC granularity, SCIM provisioning, audit logging.

5. Data Encryption & Storage — Encryption at rest (algorithm) and in transit (TLS version, FIPS 140-2). Data residency (US regions). Infrastructure provider. Multi-tenancy isolation.

6. AI/ML Disclosure — If the vendor uses generative AI or ML: AI-specific ToS, whether institutional data trains models, opt-out mechanisms.

7. Vulnerability History — Search NVD for CVEs. Check HackerOne/Bugcrowd. Search for disclosed breaches or incidents. Bug bounty program details. Breach notification timeline.

8. Technical Integration — Deployment model, data flow diagram, integration protocols (REST API, SFTP, webhooks), exchange cadence, supply chain dependencies.

9. Trust Center — Check trustpage.[vendor].com, [vendor].com/trust, [vendor].com/security.

Use web search extensively. Return detailed findings with source URLs. Distinguish verified facts from marketing claims.
```

---

## Reputation

```
Research [VENDOR]'s market reputation and company profile comprehensively. This is for a higher education institution evaluating a purchase.

Cover:

1. Analyst Recognition — Gartner Magic Quadrant placement (quadrant, year, category), Forrester Wave, IDC MarketScape. Gartner Peer Insights rating, review count, recommendation rate.

2. Review Platform Ratings — G2 (rating, category rankings, review count), Capterra (rating, reviews), TrustRadius (rating, awards), PeerSpot (pros/cons themes), Gartner Peer Insights.

3. Company Profile — Founding date, headquarters, CEO, employee count, funding history (rounds, investors, amounts), valuation, revenue (ARR), customer count, endpoints managed.

4. Recent Events — Acquisitions, executive changes, major product launches, partnerships in last 2 years. IPO plans or rumors.

5. Customer Satisfaction — Published NPS, retention rates, scale evidence, case studies (especially higher ed), awards.

6. Criticisms & Concerns — G2/Capterra 1-2 star review themes. Reddit r/sysadmin, r/msp discussions. Billing/contract complaints. Support quality issues. Product limitations vs. marketing claims.

7. Employee Reviews — Glassdoor/Indeed ratings, compensation concerns, cultural red flags that might affect product quality or company stability.

8. Controversies — Lawsuits, regulatory actions, data breaches, public controversies, BBB complaints.

Use web search extensively. Be balanced — report positives and negatives with equal rigor. Return findings with source URLs.
```

---

## Cost Analysis

```
Research [VENDOR]'s pricing, licensing model, and total cost of ownership for a higher education institution with approximately [SCALE] endpoints/users.

Cover:

1. Pricing Model — Per-device vs. per-user vs. per-technician. Tiers and what's included. Published vs. quote-only. Billing frequency options.

2. Estimated Pricing — Search Reddit, G2/Capterra pricing sections, MSP forums, comparison articles for pricing data points. Build a table across scales (50, 500, 1000, 2000, 10000+ units).

3. Educational Discounts — Edu pricing (percentage discount). Formal education program vs. ad hoc. Consortium pricing (Internet2, E&I Cooperative, EDUCAUSE). Multi-year discount tiers.

4. Included vs. Add-Ons — Base features, optional add-ons with cost premium. Training/onboarding (included or paid). Support tiers. API access. Storage/backup.

5. Contract Terms — Annual vs. multi-year. Auto-renewal and cancellation notice. Payment terms. Price escalation caps. Mid-term subscription changes. Early termination penalties.

6. Competitive Cost Comparison — Compare against 3-5 competitors at similar scale. Price per unit, what's included, model differences, hidden costs.

7. ROI Evidence — Vendor case studies with quantified savings. Forrester TEI or Nucleus Research. Community-reported savings. Automation-driven labor savings. Tool consolidation value.

8. Hidden Costs — Implementation/migration, custom integrations, training time, vendor lock-in costs, overage charges.

Use web search extensively. State confidence level for each pricing estimate. Return findings with source URLs.
```

---

## Legal & Contract

```
Research [VENDOR]'s legal terms, contracts, and regulatory compliance posture for a higher education institution.

Check these URLs: [vendor].com/terms, [vendor].com/legal, [vendor].com/privacy, [vendor].com/dpa, [vendor].com/eula, [vendor].com/sla

Cover:

1. Terms of Service — Liability caps (amount or formula), indemnification (mutual? scope?), warranty disclaimers, governing law/jurisdiction, termination provisions, force majeure.

2. Data Processing Agreement — What personal data is processed, legal basis, retention/deletion policies, sub-processor list and change notification, international transfers (SCCs), breach notification timeline, data return format and timeline, NIST 800-88 destruction.

3. FERPA Compliance — Explicit FERPA statement? Will accept "school official" under 34 C.F.R. § 99.31? Agrees to use education records only for contracted purposes?

4. GLBA Compliance — Acknowledges GLBA and FTC Red Flags? Same-day breach notification for financial data?

5. Privacy Policy — Data collected, usage, third-party sharing, aggregation/anonymization for sale, opt-outs.

6. EULA/License Agreement — IP ownership of content created in-platform, usage restrictions, end-user EULA requirements, audit rights.

7. SLA — Uptime commitment, service credits, exclusions, maintenance windows.

8. Insurance — Tech E&O / Cyber Liability coverage, limits, CoI availability.

9. Sub-processors — List URL, advance notice period, opt-out provisions.

Use web search and direct URL fetching. Return detailed findings with source URLs. Note where terms are silent on required provisions.
```

---

## Competitive Analysis

```
Research how [VENDOR] compares to its primary competitors for [PRODUCT CATEGORY] at a higher education institution. The institution currently uses [CURRENT TOOLS].

Compare against 3-5 competitors. For each:

1. Feature Comparison — Build a matrix covering: platform support (Windows, macOS, Linux, ChromeOS, iOS, Android), core features, automation/scripting, reporting, integrations, security features. Rate: Excellent / Good / Basic / Limited / Not Supported.

2. Deployment — SaaS/on-prem/hybrid, deployment timeline, agent-based vs. agentless, implementation complexity, migration path from current tools.

3. Higher Ed Adoption — Which is most used in higher ed? EDUCAUSE presence. Case studies from peer institutions. Consortium purchasing.

4. Integration Ecosystem — Azure AD, Okta, SAML/Shibboleth, ServiceNow, Zendesk, Splunk, M365, Google Workspace, Banner, Slate, Canvas, Blackbaud.

5. Strengths & Weaknesses — Where each clearly wins/loses vs. [VENDOR]. Scenarios where each is the better choice.

6. Migration — Difficulty migrating from current tools. Tool consolidation potential. Data portability. Timeline and risk.

Use web search extensively. Check G2 and TrustRadius "Compare" pages. Be fair — note where competitors genuinely excel. Return findings with source URLs.
```

---

## Higher Education Fit

```
Research how well [VENDOR] fits the specific needs of a higher education institution ([INSTITUTION DESCRIPTION]).

Cover:

1. Higher Ed Case Studies — Search [vendor].com/customer-stories and the web for universities, colleges, K-12 using [VENDOR]. Get specifics: institution name, size, scope, outcomes.

2. EDUCAUSE Presence — Search educause.edu for mentions. Conference exhibitor history. EDUCAUSE Review articles. Community discussions. Internet2 partnerships.

3. Academic Workflow Fit — Academic calendar adaptation, lab/shared device management, classroom tech, BYOD, faculty/staff lifecycle, student workers, summer operations.

4. Compliance — FERPA (school official status), GLBA (same-day breach notification), HIPAA (BAA), ADA/Section 508 (WCAG 2.0 AA, VPAT), HECVAT status.

5. Higher Ed Integrations — Banner, PeopleSoft, Canvas, Blackboard, Slate, Blackbaud, Shibboleth, InCommon, Ex Libris, StarRez, CBORD.

6. Staffing Fit — Automation out of the box, learning curve for small team, unlimited training, community of practice, generalist vs. specialist.

7. Peer Institutions — Similar-sized institutions using this product. Same category (liberal arts, R1, community college). Same region or consortium.

8. Exit Strategy — Data export, agent removal, MDM unenrollment, configuration portability, lock-in risks, grace period after termination.

Use web search extensively. Think like a campus IT director. Return findings with source URLs.
```

---

## Build Feasibility Assessment

```
Assess whether [VENDOR]'s [PRODUCT CATEGORY] product could feasibly be built in-house by a small higher education IT team augmented with agentic AI coding tools (Claude Code, GitHub Copilot, Cursor, etc.). The institution is a small liberal arts college ([INSTITUTION DESCRIPTION]) with lean IT staff.

The use case is: [USE CASE]. The data classification for this use case is: [DATA CLASSIFICATION]. The institution currently uses [CURRENT TOOLS] and has approximately [SCALE] users.

SCOPED REQUIREMENTS (evaluate against THESE, not the vendor's full product):
[SCOPED REQUIREMENTS SUMMARY - must-have features, nice-to-have features, must-have integrations, nice-to-have integrations, core workflows, pain points]

If no scoped requirements are provided above, note this limitation prominently in your assessment and flag that complexity may be overstated because you're evaluating against the vendor's full product rather than the team's actual needs.

IMPORTANT: Agentic AI coding capabilities have advanced dramatically. As of early 2026, tools like Claude Code can autonomously scaffold full-stack web applications, write database migrations, implement REST APIs, build React frontends, configure authentication, write tests, and iterate on bugs — often producing working prototypes of scoped applications in days, not months. Use current capability estimates, not 2023-era assumptions.

Investigate and report on:

1. Application Complexity — Start from the SCOPED REQUIREMENTS above, not the vendor's full feature page. List the vendor's features for context, but mark each as NEEDED / NICE-TO-HAVE / NOT NEEDED based on the scoped requirements. Define the minimum viable feature set. Rate each NEEDED feature: trivial / moderate / complex / very complex. Calculate a scoped complexity score based on needed features only. Search GitHub for open-source alternatives ("[vendor] open source alternative", "[product category] self-hosted").

2. Data Sensitivity — What data elements does the product typically manage? Classify each as Public, Internal, Restricted, or Confidential per higher ed data security policy. If any element is Restricted or higher, document the specific regulatory framework (FERPA, HIPAA, GLBA, PCI-DSS). Could an in-house version be architected to avoid handling sensitive data categories?

3. Architecture Requirements — Estimate what self-hosting the SCOPED feature set would require (not the vendor's full product):
   - Frontend: framework complexity (static site, SPA, real-time collaborative)
   - Backend: API complexity, business logic depth, background processing
   - Database: schema complexity, estimated data volume
   - Infrastructure: hosting model (single VPS? Kubernetes? managed services?), estimated monthly cost
   - Integrations: only the MUST-HAVE integrations from the scoped requirements
   Search for "[product category] tech stack" and "[product category] architecture" to understand typical implementations.

4. AI-Assisted Development Estimate — For the SCOPED feature set:
   - Could an agentic AI coding tool (Claude Code, Cursor) build a working prototype? Standard patterns like task boards, dashboards, CRUD APIs, and auth flows are well within current AI capabilities.
   - Realistic timeline: use current AI capability benchmarks, not traditional estimates. A scoped 8-feature CRUD app with SSO is typically 1-2 weeks of AI-assisted development, not 6 months.
   - What percentage of the scoped features map to patterns AI handles well (CRUD, dashboards, APIs, forms, auth)?
   - What requires human judgment? (security review, UX design, infrastructure ops, compliance validation)
   - Also assess AI-assisted maintenance: bug fixes and updates are faster with AI tools (estimate 10-20 hrs/month, not 40).

5. Open-Source Alternatives — Search for self-hosted open-source alternatives to [VENDOR]. For each, report: name, GitHub stars, last commit date, license, feature coverage vs. the SCOPED requirements (not the vendor's full product), hosting requirements, community size. Could an OSS project serve as a foundation instead of building from scratch?

6. Maintenance Burden — Estimate ongoing costs with AI-assisted maintenance: security patching (hours/month), bug fixes (hours/month), infrastructure monitoring, compliance maintenance, dependency updates. AI tools significantly reduce maintenance time compared to traditional development. What happens when the primary maintainer leaves? Is this sustainable?

7. TCO Comparison — Build a 3-year and 5-year total cost comparison across THREE scenarios:
   - Buy: annual licensing at [SCALE] (use the tier that covers needed features, not the most expensive), implementation, training, support
   - Build (AI-assisted): AI-assisted development hours × $80/hr loaded rate (use realistic AI-assisted timelines, not traditional), AI tool subscriptions, infrastructure monthly costs, AI-assisted maintenance hours/month × $80/hr, opportunity cost
   - OSS (if viable alternative exists): infrastructure costs, customization time, ongoing maintenance
   Present all three honestly. Don't inflate build estimates to justify a predetermined conclusion.

8. Risk Assessment — Compare risks of each path:
   - Buy risks: vendor failure, price escalation, data breach liability, lock-in, feature divergence, paying for features you don't use
   - Build risks: scope creep, key-person dependency, security vulnerabilities, compliance gaps, maintenance fatigue
   - OSS risks: project abandonment, community size, upgrade complexity, gap-filling effort

Decision Framework:
- STRONGLY FAVOR BUY if: data is Restricted/Confidential, scoped feature set is genuinely complex (15+ features with deep business logic), architecture requires enterprise infrastructure, or regulatory compliance burden is high
- LEAN TOWARD BUY if: moderate scoped complexity with some sensitive data, or total AI-assisted build cost still exceeds 2x vendor cost over 3 years
- BUILD WITH CAVEATS if: scoped feature set is manageable (8-12 features), internal/public data only, viable OSS foundation exists, team has someone who can review AI-generated code
- BUILD VIABLE if: scoped feature set is simple (3-7 features), public/internal data only, AI agent can scaffold it in 1-2 weeks, and maintenance burden is low with AI assistance

Use web search extensively. Be honest in BOTH directions — don't underestimate complexity, but don't overestimate it by evaluating the vendor's full product when the team only needs a fraction. Return detailed findings with source URLs.
```
