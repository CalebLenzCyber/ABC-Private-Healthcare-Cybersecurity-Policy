# ABC Private Healthcare: Enterprise Cybersecurity Policy & Governance Framework

A technical cybersecurity policy written for a **fictional** healthcare organization, ABC Private Healthcare. It sets baseline security controls for the IT department and Security Operations Center (SOC), with an emphasis on protecting electronic Protected Health Information (ePHI).

> **Note:** ABC Private Healthcare is a fictional company created for a course project. No real organization, systems, or data are described.

## 📄 Read the policy

- **[Read online (Markdown)](policy/cybersecurity-policy.md)**
- **[Download PDF](policy/ABC_Private_Healthcare_Cybersecurity_Policy.pdf)**

## What it covers

| Section | Topic | Highlights |
|---|---|---|
| 1 | Governance | Authority, scope, audience, annual review, exception process |
| 2 | Network security | VLAN segmentation, deny-by-default inter-VLAN traffic, VPN + MFA remote access, device hardening, patching |
| 3 | Web security | WAF, TLS requirements, secure admin interfaces, vulnerability testing and remediation |
| 4 | Email security | SPF, DKIM, DMARC, secure email gateways, phishing containment |
| 5 | Mobile devices | UEM/MDM enrollment, BYOD standards, app sandboxing |
| 6 | Physical security | Tiered zones, environmental monitoring, surveillance and logging |
| 7 | Operational security | Endpoint protection (EDR), kiosks, encrypted and immutable backups |
| 8 | Compliance and response | SIEM monitoring, enforcement, incident response |
| 9 | References | APA 7th edition |

## Frameworks and standards referenced

- NIST SP 800-53 Rev. 5, 800-41, 800-40 Rev. 4, and 800-177 Rev. 1
- CIS Critical Security Controls v8.1
- CISA Cross-Sector Cybersecurity Performance Goals (CPG 2.0)
- HIPAA Security Rule (45 CFR § 164.312)
- IEEE 802.1X-2020

## Skills demonstrated

- Writing enforceable, auditable security policy (clear "shall" requirements, scope, and exception handling)
- Mapping controls to NIST, CIS, CISA, and HIPAA requirements
- Healthcare-specific risk thinking: segmentation of clinical systems, ePHI protection, ransomware resilience
- Network, email, endpoint, mobile, and physical security design

## Possible future improvements

- Add a control-mapping table (policy section → NIST / CIS / HIPAA control IDs)
- Add an incident response procedure and severity matrix
- Add a risk assessment and asset inventory to justify the controls

## License

This work is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
