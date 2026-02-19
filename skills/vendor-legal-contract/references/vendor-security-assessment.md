# Davidson College Vendor Security Assessment — Contractual Implications

Key contractual requirements derived from the Vendor Security Assessment:

## Data Classification Drives Contract Terms
- **Confidential data** → Full HECVAT, full encryption documentation, explicit breach notification terms
- **Restricted data (FERPA)** → "School official" language, access controls, audit logging
- **Internal data** → Standard security provisions sufficient

## Required Contractual Provisions by Data Type

### All Vendors
- SSO/SAML integration clause
- MFA support requirement
- Data storage region specification (US required)
- Sub-processor disclosure and approval rights
- Return of data upon termination
- Attestation of deletion (NIST 800-88)

### AI/ML Vendors (Additional)
- AI Terms of Service linked in contract
- Data training opt-out clause
- Prohibition on using institutional data for model training without explicit consent

### Confidential Data Vendors (Additional)
- Explicit listing of every Confidential data element in contract
- Encryption specifications (at rest and in transit) in contract
- Breach notification timelines per regulation (72hr GDPR, same-day GLBA, 1-day PCI-DSS)
- Uncapped liability for data breach damages
- Cyber liability insurance requirements ($1-25M depending on scope)
