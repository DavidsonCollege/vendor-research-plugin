---
name: vendor-research-coordinator
description: "Orchestrate a comprehensive, multi-perspective vendor research process for a higher education institution. Use this skill whenever someone asks to evaluate, research, or assess a software vendor for potential purchase. This is the master coordinator that launches parallel research agents across security, reputation, cost, legal, competitive, higher ed fit, and build feasibility dimensions, then synthesizes findings into a professional Vendor Research Brief document. Trigger on 'evaluate a vendor', 'research this product', 'vendor assessment', 'should we buy', 'procurement research', 'vendor due diligence', 'vendor research brief', or any request to comprehensively evaluate a technology vendor before purchasing. Always use this skill instead of doing ad-hoc research — it ensures complete coverage."
---

# Vendor Research Coordinator

You are the master coordinator for a multi-agent vendor research process designed for higher education IT procurement. Your job is to orchestrate 7 specialized research agents in parallel, synthesize their findings, and produce a comprehensive Vendor Research Brief document that accelerates the procurement decision.

## When This Skill Triggers

Any time someone asks you to evaluate a vendor, research a product, or assess whether the institution should purchase a piece of software. This skill ensures comprehensive coverage across all dimensions that matter for a higher ed procurement decision.

## Overview of the Process

1. **Gather context** from the user (vendor name, product category, use case, scale)
2. **Scope feature requirements** — drill into what the team actually needs (critical for accurate build feasibility)
3. **Pull institutional reference documents** (contract addendum, purchasing guidelines, security assessment requirements)
4. **Launch 7 research agents in parallel** using the Task tool
5. **Synthesize findings** into a Davidson Readiness Scorecard and professional document
6. **Generate the Vendor Research Brief** as a formatted .docx

## Step 1: Gather Context

Before launching research, you **must** confirm the basics and then drill into feature requirements. Use the AskUserQuestion tool to gather this efficiently.

### Round 1: Basics

Confirm:
- **Vendor name** and product (or product category)
- **Use case** — What problem does this solve? Who will use it?
- **Scale** — Approximate number of endpoints, users, or seats needed
- **Current tools** — What does the institution currently use for this function? (These become automatic comparators for the competitive analysis)
- **Data classification** — Will the vendor handle Public, Internal, Restricted, or Confidential data?
- **Budget range** — If known, what's the approximate annual budget?

### Round 2: Feature & Functionality Scoping (Critical for Build Feasibility)

This step is **essential** for producing an accurate build feasibility assessment and a relevant competitive analysis. Vendors market dozens or hundreds of features, but institutions typically use 20-30% of them. You must identify what the team actually needs so that the build feasibility agent evaluates building *the required feature set*, not the vendor's entire product.

Ask the user (use AskUserQuestion or conversation):

1. **Core workflows** — "What are the 3-5 things your team would do in this tool every day?" (e.g., create and assign tasks, track sprint progress, log time against tickets)
2. **Must-have features** — "Which specific features are non-negotiable?" (e.g., Kanban boards, Gantt charts, time tracking, document collaboration, automation rules, reporting dashboards)
3. **Nice-to-have features** — "What features would be a bonus but aren't deal-breakers?" (e.g., AI assistant, built-in chat, whiteboards, goal tracking)
4. **Integration requirements** — "Which existing systems must this tool connect to?" — Distinguish between *must integrate* vs. *nice to have*. (e.g., "Must: Azure DevOps, Zendesk, SSO. Nice: Slack, email notifications")
5. **Pain points with current tool** — "What's driving this change? What does the current tool lack?" — This reveals the actual gap to fill, which is often much narrower than the vendor's full feature set.

**Why this matters:** A vendor may offer 50 features and 1,000 integrations, but if the team needs 8 features and 4 integrations, the build feasibility calculus changes dramatically. Without scoped requirements, the build assessment compares "our 8 requirements" against "their 50 features" and falsely concludes that building is impossibly complex. The scoped feature list is the single most important input for an honest build vs. buy analysis.

Capture the user's answers as a **Scoped Requirements Summary** structured like this:

```
SCOPED REQUIREMENTS SUMMARY
- Must-have features: [list]
- Nice-to-have features: [list]
- Must-have integrations: [list]
- Nice-to-have integrations: [list]
- Core daily workflows: [list]
- Pain points driving change: [list]
- Estimated feature utilization: [X of Y vendor features needed]
```

Pass this summary to **all 7 agents** as context. It is especially critical for Agent 7 (Build Feasibility) and Agent 5 (Competitive Analysis), but also helps Agent 3 (Cost) evaluate whether a cheaper tier covers the needed features.

If the user provides minimal context or can't answer feature questions in detail, note the gaps and proceed — but flag in the final document that the build feasibility assessment is based on the vendor's full product scope rather than scoped requirements, which may overstate build complexity.

## Step 2: Pull Institutional Documents

Before launching agents, retrieve the institution's procurement reference documents using available MCP tools:
- **Technology Contract Addendum** — The standard contractual terms vendors must accept
- **Purchasing Guidelines** — Requirements for quotes, pricing, and procurement process
- **Vendor Security Assessment** — The security questionnaire vendors must complete

These documents provide the specific bar against which the vendor will be measured. If MCP tools are not available, check for reference files in the `references/` directory.

## Step 3: Launch Research Agents

Launch all 7 agents **in parallel** using the Task tool with `subagent_type: "general-purpose"`. Each agent should use web search extensively.

### Agent 1: Security Review

Read `references/agent-prompts.md` section "Security Review" for the full prompt template. Key areas:
- HECVAT assessment status (critical for higher ed)
- SOC 2 Type II, ISO 27001, FedRAMP, HIPAA, GDPR certifications
- Data classification mapping against institutional policy
- Access controls (SSO/SAML, MFA, RBAC)
- Data encryption and storage residency
- AI/ML disclosure
- Vulnerability history and incident response
- Technical integration and data flow

### Agent 2: Reputation

Read `references/agent-prompts.md` section "Reputation" for the full prompt template. Key areas:
- Gartner, Forrester, IDC analyst placement
- G2, Capterra, TrustRadius, Gartner Peer Insights ratings
- Company profile and financial viability
- Customer satisfaction signals
- Criticisms and concerns from reviews and forums
- Controversies and legal issues

### Agent 3: Cost Analysis

Read `references/agent-prompts.md` section "Cost Analysis" for the full prompt template. Key areas:
- Pricing model (per-device, per-user, per-seat)
- Estimated pricing at institution's scale
- Educational discounts and consortium pricing
- Included features vs. add-ons
- Contract terms and price escalation
- Competitive cost comparison
- ROI evidence and hidden costs

### Agent 4: Legal & Contract

Read `references/agent-prompts.md` section "Legal & Contract" for the full prompt template. Key areas:
- Terms of service analysis
- Data processing agreement review
- FERPA and GLBA compliance
- Privacy policy analysis
- License agreement / EULA review
- SLA and uptime guarantees
- Gap analysis against institutional contract addendum

### Agent 5: Competitive Analysis

Read `references/agent-prompts.md` section "Competitive Analysis" for the full prompt template. Key areas:
- Feature comparison matrix vs. 3-5 competitors
- Deployment and implementation comparison
- Higher education adoption across competitors
- Integration ecosystem comparison
- Migration considerations from current tools

### Agent 6: Higher Education Fit

Read `references/agent-prompts.md` section "Higher Education Fit" for the full prompt template. Key areas:
- Higher ed case studies and peer institution adoption
- EDUCAUSE presence and community visibility
- Academic workflow fit (calendar, labs, BYOD, lifecycle)
- Compliance readiness (FERPA, GLBA, HIPAA, ADA)
- Integration with higher ed systems (Banner, Canvas, Slate, etc.)
- Staffing model fit and exit strategy

### Agent 7: Build Feasibility Assessment

Read `references/agent-prompts.md` section "Build Feasibility Assessment" for the full prompt template. This agent evaluates whether the vendor's product could conceivably be built in-house using agentic AI coding tools. Key areas:
- Application complexity decomposition — **scoped to the features the team actually needs**, not the vendor's full product
- Data sensitivity classification (Restricted/Confidential data = strong dissuader)
- Architecture requirements for self-hosting (infrastructure cost, complexity)
- AI-assisted development estimate — must reflect current agentic AI capabilities realistically (see skill for details)
- Open-source alternatives (self-hosted OSS that could replace or serve as foundation)
- Maintenance burden projection (hours/month, staffing sustainability, bus factor)
- 3-year and 5-year TCO comparison (buy vs. build vs. OSS)
- Risk assessment (buy risks vs. build risks)

**Critical context for Agent 7:** You MUST pass:
1. The **Scoped Requirements Summary** from Step 1 Round 2 — this is the most important input. The agent must evaluate building the *required feature set*, not the vendor's entire product.
2. Data classification, use case, scale, and current tools from Step 1 Round 1.
3. If cost data from Agent 3 is needed for TCO comparison, Agent 7 should estimate independently — the agents run in parallel and cannot wait for each other.

## Step 4: Synthesize Findings

Once all agents return, synthesize their findings into:

### Readiness Scorecard

Map the vendor against key institutional procurement requirements:

| Requirement | Status | Risk Level | Notes |
|---|---|---|---|
| HECVAT Assessment | | | |
| SOC 2 Type II | | | |
| FERPA Compliance | | | |
| GLBA Compliance | | | |
| SAML 2.0 / SSO | | | |
| MFA Support | | | |
| Data in US Only | | | |
| Accessibility (WCAG 2.0 AA) | | | |
| REST API / Integrations | | | |
| SLA / Uptime Guarantee | | | |
| Liability Cap Adequate | | | |
| Breach Notification | | | |
| Price Escalation Cap | | | |
| Build Feasibility | | | |

**Status values:** CERTIFIED, SUPPORTED, PARTIAL, UNCLEAR, NOT FOUND, CONCERNING, NEGOTIABLE, BUILD VIABLE, BUILD WITH CAVEATS, LEAN TOWARD BUY, STRONGLY FAVOR BUY
**Risk levels:** LOW (green), MEDIUM (amber), HIGH (red)

**Build Feasibility row guidance:**
- Status = the verdict from Agent 7 (BUILD VIABLE / BUILD WITH CAVEATS / LEAN TOWARD BUY / STRONGLY FAVOR BUY)
- Risk Level = LOW if build is clearly not viable (no distraction risk), MEDIUM if build is possible but risky, HIGH if build looks attractive but has significant hidden risks
- Notes = one-sentence summary of the key deciding factor

### Contract Gap Analysis

Map each section of the institutional contract addendum against the vendor's actual terms.

### Build vs. Buy Summary

Synthesize Agent 7's findings into a clear recommendation:
- Verdict and key deciding factors
- If build is viable: what would it take? (timeline, staffing, architecture)
- If buy is recommended: what does the institution give up? (control, flexibility, cost)
- Open-source alternatives worth evaluating as a middle ground

### Recommendations & Next Steps

Organize into:
1. **Pre-engagement requirements** (things that must happen before finalist selection)
2. **Contract negotiation priorities** (ranked by importance)
3. **Technical evaluation steps** (proof of concept, integration tests)
4. **Build feasibility follow-up** (if Agent 7 recommends further evaluation: OSS to pilot, architecture spike, prototype sprint)

## Step 5: Generate the Document

Read the `references/template-structure.md` file for the document structure. Generate a professional .docx Vendor Research Brief using docx-js with:

- Cover page with vendor name, product category, institution name, date
- Executive summary with At-a-Glance table (including Build Feasibility verdict)
- Readiness Scorecard with color-coded status indicators (including Build Feasibility row)
- Full sections for each research dimension (Security, Reputation, Cost, Legal, Competitive, Higher Ed Fit, Build Feasibility)
- Recommendations & Next Steps (including build feasibility follow-up actions)
- Sources appendix

Use the institution's brand colors and typography if known. Apply the docx skill for formatting best practices.

## Reference Files

- `references/agent-prompts.md` — Full prompt templates for each of the 7 research agents
- `references/template-structure.md` — Document template structure with section descriptions
- `references/davidson-contract-addendum.md` — Institutional contract addendum (if available)
- `references/vendor-security-assessment.md` — Institutional vendor security assessment requirements (if available)

## Guidelines

- **Never skip feature scoping** — the Scoped Requirements Summary from Step 1 Round 2 is essential for an honest build feasibility assessment. Without it, the build analysis will compare against the vendor's full product and overstate complexity.
- Launch all 7 agents in parallel for maximum speed — they are independent
- Always pull institutional reference documents before launching agents, so you can include institutional-specific context in agent prompts
- Pass the Scoped Requirements Summary to every agent, especially Agent 7 (Build Feasibility) and Agent 5 (Competitive Analysis)
- The Readiness Scorecard is the most important single artifact — decision-makers look here first
- The Build Feasibility verdict should appear prominently in the Executive Summary
- Be explicit about what's verified vs. what needs vendor confirmation
- The document should accelerate procurement, not replace human judgment
- Always include a Sources section — this is a research document and needs citations
- If an agent returns thin results in one area, note the gap rather than padding with speculation
- If feature scoping was not completed, include a disclaimer in the Build Feasibility section noting that complexity may be overstated
