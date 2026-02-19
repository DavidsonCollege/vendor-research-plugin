# Vendor Research Plugin

A comprehensive, multi-agent vendor research toolkit designed for higher education IT procurement. When triggered, this plugin launches 7 specialized research agents in parallel to evaluate a software vendor across security, reputation, cost, legal, competitive, higher-ed fit, and build feasibility dimensions, then synthesizes the findings into a professional Vendor Research Brief document.

## Installation

```bash
claude plugin add DavidsonCollege/vendor-research-plugin
```

Or from within Claude Code:

```
/plugin add DavidsonCollege/vendor-research-plugin
```

## What It Does

Say something like "Evaluate NinjaOne for purchase" or "Research Zoom as a vendor" and the coordinator skill will:

1. Gather context about your use case and scale
2. Pull your institution's contract addendum and purchasing guidelines
3. Launch 7 parallel research agents using web search
4. Synthesize findings into a Readiness Scorecard
5. Generate a branded .docx Vendor Research Brief

## Skills

| Skill | Trigger Phrases | Purpose |
|-------|----------------|---------|
| **vendor-research-coordinator** | "evaluate a vendor", "research this product", "vendor assessment", "should we buy" | Master orchestrator that runs all 7 agents and produces the final document |
| **vendor-security-review** | "vendor security", "HECVAT", "SOC 2 review", "compliance check" | HECVAT, certifications, data classification, access controls, encryption, CVEs |
| **vendor-reputation** | "vendor reputation", "customer reviews", "Gartner rating" | Analyst recognition, review platforms, financials, customer concerns |
| **vendor-cost-analysis** | "vendor pricing", "educational discount", "TCO", "cost comparison" | Pricing models, edu discounts, ROI, competitive cost comparison |
| **vendor-legal-contract** | "contract review", "DPA", "FERPA compliance", "liability cap" | ToS, DPA, FERPA/GLBA, privacy, EULA, SLA, addendum gap analysis |
| **vendor-competitive-analysis** | "compare vendors", "alternatives to", "feature comparison" | Feature matrix, deployment, higher ed adoption, migration |
| **vendor-higher-ed-fit** | "higher ed fit", "university use", "EDUCAUSE", "campus deployment" | Case studies, academic workflows, compliance, peer institutions |
| **vendor-build-feasibility** | "build vs buy", "could we build this", "in-house development", "agentic AI alternative" | Complexity analysis, OSS alternatives, TCO comparison, AI dev feasibility |

## What's New in v0.2.0

- **Build Feasibility Assessment** — New 7th agent evaluates whether a vendor's product could be built in-house using agentic AI coding tools. Considers data sensitivity (FERPA/HIPAA = don't build), application complexity, self-hosting architecture, open-source alternatives, maintenance burden, and 3-year/5-year TCO comparison. Produces a verdict on a 4-point scale: BUILD VIABLE, BUILD WITH CAVEATS, LEAN TOWARD BUY, STRONGLY FAVOR BUY.
- **Updated Readiness Scorecard** — Now includes a Build Feasibility row with color-coded verdict
- **Updated Executive Summary** — At-a-Glance table includes build feasibility verdict
- **Updated Recommendations** — Includes build feasibility follow-up actions when relevant

## Assets

- `assets/Vendor_Research_Brief_Template.docx` — Generic template with placeholder text for all sections

## Customization

The security and legal skills include reference files with Davidson College's specific requirements (HECVAT version logic, data classification policy, contract addendum provisions). To adapt for another institution:

1. Update `skills/vendor-security-review/references/vendor-security-assessment.md` with your institution's security assessment requirements
2. Update `skills/vendor-legal-contract/references/vendor-security-assessment.md` with your contractual security provisions
3. Optionally add a `references/contract-addendum.md` to the legal skill with your institution's standard contract addendum

## Usage

Individual skills can be triggered independently (e.g., just run a security review, or just assess build feasibility) or the coordinator can run all seven in parallel for a comprehensive assessment. The coordinator is the recommended entry point for full vendor evaluations.
