# Davidson College Vendor Security Assessment Requirements

This document defines the security review requirements that all vendors must satisfy. Use this as a checklist when evaluating a vendor's security posture.

## 1. Security Self-Assessment (HECVAT)

- **Primary evaluation tool**: Higher Education Community Vendor Assessment Toolkit (HECVAT), developed by EDUCAUSE HEISC
- **Requirement**: Completed HECVAT (Version 4.x preferred)
- **Full Version required** if: software processes payments (PCI-DSS) OR handles Confidential data per Davidson Data Security Policy
- **Lite Version acceptable** if: no payments processed AND data classified as Internal or Public
- **Recency**: Must be completed or updated within the last 18 months
- **Resource**: EDUCAUSE HECVAT page (educause.edu)

## 2. Compliance & Third-Party Audits

- **SOC 2 Type II Report**: Highly preferred (evidence of operational effectiveness over time)
- **Alternative Certifications**: ISO/IEC 27001, NIST 800-171, Cloud Security Alliance (CSA) STAR registry
- **Security Trust Center**: Vendor must provide URL to public-facing security/trust page

## 3. Business Context & Access Control

- **Use Case**: High-level description of application purpose and business problem solved
- **User Personas**: Identify groups (students, faculty, IT staff) and access levels (Read-Only, Contributor, System Admin)
- **Access Management**: How access is provisioned, de-provisioned, and audited
- **SSO/MFA**: Integration with Davidson SSO/MFA via SAML/Shibboleth is strongly preferred
- **Native MFA**: Does the application natively support multifactor authentication?

## 4. Data Classification & Privacy

All data must be classified per Davidson Data Security Policy:

| Classification | Definition | Examples |
|---|---|---|
| **Public** | May be shared freely with campus and general public | Directory info, public events |
| **Internal** | Restricted to internal access; disclosure would not violate laws or cause reputational harm | Internal memos, departmental notes |
| **Restricted** | Shared only with specific individuals with business need or FERPA-protected | Student ID numbers, donor amounts |
| **Confidential** | Protected by state/federal privacy or data security laws | SSNs, health records, financial account numbers |

**If Confidential data is involved**: Explicitly list every data element and describe encryption methods for data at rest and in transit.

## 5. Data Storage

- In which region(s) (e.g., US-East, US-West) will Davidson data be stored at rest?
- Are backups stored in the same region as production data?

## 6. Artificial Intelligence (AI) Disclosure

If the application uses Generative AI or machine learning:
- **AI Terms of Service**: Links to AI/ML-specific privacy policies
- **Data Usage**: Whether Davidson data trains the vendor's or sub-processors' models
- **Opt-Out**: Mechanism to opt out of model training while maintaining functionality

## 7. Technical Integration & Data Flow

- **Deployment**: On-prem, vendor-hosted, or integration
- **Data Flow Diagram**: Visual of how data moves between Davidson and vendor (and any sub-processors)
- **Integration Methods**: Technical protocols (REST API, SFTP, Webhooks)
- **Cadence**: Frequency of data exchanges (real-time, nightly batch, one-time migration)
- **Supply Chain**: Third-party vendor dependencies (e.g., AWS hosting)

## 8. Contractual Details

- **Contract Length**: Intended term (1, 3, or 5 years)
- **Termination**: "Return of Data" policy upon contract end
- **Data Deletion**: Attestation of deletion confirming removal of Davidson data including backups
