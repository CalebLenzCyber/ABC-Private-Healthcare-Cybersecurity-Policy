# Enterprise Information Technology Cybersecurity Policy and Governance Framework

**ABC Private Healthcare**

**Version: 1.0**

**Document Classification: Internal Use Only**

## Section 1: Introduction and Administrative Governance

- **1.1 Authority:** This document is established under the explicit authority of the Chief Information Security Officer (CISO) and the Enterprise Security Board. This policy acts as a mandatory charter for the internal Information Technology (IT) department and the Security Operations Center (SOC).

- **1.2 Purpose and Scope**

- The purpose of this document is to assist IT and SOC personnel in implementing, monitoring, and maintaining baseline security controls across all organizational systems.

- **1.2.1 In-Scope Assets**: The boundary of authority defined by this policy encompasses all enterprise computing environments owned, operated, leased, or managed by the organization. This baseline addresses standard infrastructure using general operating systems (OS) such as Windows, Linux, and Unix variants. It applies uniformly to:

- **Specialized Endpoints:** Standard client workstations, managed mobile hardware, and specialized public-facing transaction systems or kiosks.

- **Core Server Infrastructure:** Publicly accessible, outward-facing production servers (e.g., dedicated web assets, electronic mail hosts) and all inward-facing internal directory, database, and staging servers.

- **Network Infrastructure**: All local area networks (LANs), wide area networks (WANs), software-defined networks (SDNs), and virtual local area networks (VLANs).

- **Cloud Architectures**: All multi-tenant public, private, or hybrid Infrastructure-as-a-Service (IaaS) and Platform-as-a-Service (PaaS) deployments.

**1.2.2 Out of Scope Assets:** Hosts that incidentally provide minor administrative background services (e.g., an isolated remote access link used temporarily for out-of-band hardware troubleshooting) are not covered under these general server guidelines. Furthermore, highly specialized security infrastructure devices—specifically enterprise Next-Generation Firewalls (NGFW), standalone Intrusion Detection Systems (IDS), and proprietary storage area network (SAN) appliances—possess unusual configurations and hyper-specific security needs. These environments are considered outside the scope of this baseline document and are governed by dedicated security engineering charters.

- **1.3 Audience:** This document is created exclusively for system administrators, network engineers, cloud architects, and SOC analysts who are responsible for the hands-on, technical aspects of securing the enterprise. The material within this document is highly technical and operational. It assumes that the reader possesses professional certifications or equivalent foundational competencies in system architecture, cryptographic protocols, and network security.

- **1.3.1 Mandatory Annual Review:** This framework must undergo a formal audit review, and re-authorization process every twelve (12) calendar months. This cycle ensures alignment with updated regulatory requirements, Center for Internet Security (CIS) Controls, and Cybersecurity and Infrastructure Security Agency (CISA) Performance Goals.

- **1.3.2 Policy Exceptions:** Exceptions to this policy must be documented, justified by business or operational requirements, approved by the Information Technology Manager and designated Information Security Officer, and reviewed annually.

## Section 2: Network Security Policy (Infrastructure and Servers)

- **2.1 Architecture and Segmentation**: The organization shall implement a layered network architecture designed to protect electronic Protected Health Information (ePHI), business systems, and administrative resources from unauthorized access.

- **2.1.1 Network Segmentation Requirements:** The enterprise network shall be logically segmented through the use of Virtual Local Area Networks (VLANs) and access control policies. At a minimum, the following network segments shall exist:

  - **Clinical Systems VLAN:** Devices used for patient scheduling, electronic health records (EHR), and healthcare management applications.

  - **Administrative VLAN:** Systems used for accounting, human resources, payroll, and executive operations.

  - **Server VLAN:** Internal application servers, database servers, domain controllers, and network management systems.

  - **Guest Wireless VLAN:** Isolated internet-only access for visitors and non-corporate devices.

  - **Management VLAN:** Dedicated connectivity for network infrastructure devices and system administration activities.

> Traffic between VLANs shall be denied by default and permitted only through documented business requirements approved by IT management. Network segmentation controls shall align with NIST system and communications protection requirements and CISA Cross-Sector Cybersecurity Performance Goals regarding least-privilege network access and reduction of lateral movement. (NIST SP 800-53 Rev. 5; CISA CPG 2.0)

- **2.1.2 Remote Connectivity:** Remote connectivity to organizational resources shall only occur through approved Virtual Private Network (VPN) technology utilizing:

  - AES-256 encryption

  - Multi-Factor Authentication (MFA)

  - Role-based access controls

  - Session timeout and automatic disconnection mechanisms.

> Direct Exposure of Remote Desktop Protocol (RDP), Secure Shell (SSH), or other management services to the public is prohibited.

- **2.2 Infrastructure Hardening**: All network infrastructure devices shall adhere to a standardized hardening baseline established and maintained by the IT department.

- **2.2.1** Secure Configuration Standards: Network devices shall be configured according to vendor security best practices and organizational standards.

  - Minimum Requirements Include:

    - Removal or disabling of default accounts.

    - Modification of default vendor passwords.

    - Use of secure management protocols such as SSH and HTTPS

    - Disabling Telnet, HTTP, and other unencrypted management services.

    - Disabling unused interfaces, services, and protocols.

    - Restricting administrative access to authorized management networks.

- **2.2.2 Firewall Requirements:** Firewalls shall function under a principle of least privilege.

  - Firewall Configurations Shall:

    - Deny all inbound traffic by default.

    - Allow only approved business services.

    - Log all denied connection attempts.

    - Maintain automated backups of configuration files.

    - Undergo quarterly rule review and validation.

For cloud-hosted infrastructure, equivalent security group or firewall policies shall be implemented.

- **2.2.3 Secure DNS and Email Protection:** The organization shall implement:

  - DNS filtering to reduce access to known malicious domains.

  - Email filtering and anti-phishing protections.

  - Domain-based Message Authentication, Reporting and Conformance (DMARC).

  - Sender Policy Framework (SPF)

  - DomainKeys Identified Mail (DKIM)

> These controls support protection against phishing, business email compromise, and malware delivery.

- **2.3 Server Considerations**: Servers supporting business operations or storing ePHI shall be maintained according to secure baseline configuration standards.

- **2.3.1 Operating System Hardening:** All Windows and Linux servers shall:

  - Operate using supported operating system versions

  - Remove unnecessary software and services.

  - Enforce host-based firewalls.

  - Utilize endpoint detection and response (EDR) solutions.

  - Maintain centralized logging capabilities.

- **2.3.2 Patch and Vulnerability Management:** The IT department shall maintain a formal patch management process.

  - Critical security patches shall be deployed within fourteen (14) calendar days of release. This requirement supports NIST enterprise patch management guidance and CIS Control 7 Continuous Vulnerability Management practices.

  - High-risk vulnerabilities shall be remediated within thirty (30) calendar days.

  - Monthly vulnerability scans shall be conducted against internal and external assets.

  - Scan results shall be documented and reviewed by IT management.

> Emergency patching procedures may be initiated when active exploitation or severe security risks are identified.

- **2.3.3 Account and Access Management:** Access to servers shall follow the principle of least privilege.

  - Requirements Include:

    - Unique user accounts for all personnel.

    - Prohibition of shared administrator accounts.

    - MFA for privileged access.

    - Role-Based Access Control (RBAC).

    - Quarterly review of privileged accounts.

> Administrative access shall be logged and retained according to organizational record-retention requirements.

- **2.3.4 Backup and Recovery:** Servers containing organizational data or ePHI shall be included within approved backup procedures.

  - Backup requirements include:

    - Daily automated backups.

    - Encryption of backup data at rest and in transit

    - Off-site or cloud-based backup storage.

    - Quarterly restoration testing.

    - Retention periods aligned with legal and healthcare regulatory requirements.

- **2.4 Network Access Control (NAC)**: The organization shall implement mechanisms to ensure that only authorized devices and users are permitted network connectivity.

- **2.4.1 Device Authentication:** Network access shall require authentication through IEEE 802.1X or an equivalent NAC solution to ensure only authenticated and authorized devices gain access to enterprise resources

  - Authorized Devices Shall:

    - Be organization-owned or formally approved.

    - Run supported operating systems.

    - Maintain current antivirus or EDR protection.

    - Comply with security configuration standards.

Devices failing validation shall be automatically quarantined or denied access.

- **2.4.2 Wireless Security:** Corporate wireless networks shall:

  - Utilize WPA3 Enterprise encryption.

  - Require individual user authentication.

  - Enforce network segmentation from guest wireless networks.

  - Disable insecure wireless protocols and shared credentials.

> Guest wireless access shall be isolated from all internal organizational resources.

- **2.4.3 Security Incident Reporting:** Suspicious device activity, failed authentication events, unauthorized network connections, or suspected compromise shall be immediately reported to the Security Operations Center (SOC) or designated IT security personnel.

> Incident response activities shall follow the organization's Incident Response Plan and applicable healthcare regulatory reporting requirements.

## Section 3: Web Security Policy (Internal and External)

- **3.1 External Web Asset Protection**: Public-facing web assets present a significant attack surface and shall be secured through multiple overlapping defense mechanisms. All internet-facing web applications, websites, patient portals, application programming interfaces (APIs), and cloud-hosted services shall be protected through a defense-in-depth security model consistent with NIST security controls and CISA Cybersecurity Performance Goals.

- **3.1.1 Web Application Firewall (WAF):** All public-facing web applications shall be protected through a Web Application Firewall (WAF) capable of inspecting and filtering web traffic.

  - The WAF shall:

    - Monitor inbound and outbound HTTP/HTTPS traffic.

    - Detect and block common web attacks, including SQL injection, cross-site scripting (XSS), and command injection attempts.

    - Log security events and suspected attack activity.

    - Receive security signature and rule updates on a regular basis.

    - Integrate with centralized log management and monitoring systems.

> WAF configuration shall be reviewed semi-annually and after significant application changes. This requirement aligns with NIST system and protection controls and CIS secure configuration recommendations.

- **3.2 Internal Web Services**: Internal applications supporting business operations, clinical workflows, administration, and employee collaboration shall be secured according to enterprise security standards.

- **3.2.1 Secure Communication Requirements:** All internal web services shall utilize encrypted communications.

  - Requirements Include:

    - HTTPS enforced for all web services.

    - TLS version 1.3 minimum.

    - Organization-approved certificates.

    - Automated certificate expiration monitoring.

    - Redirection of all unsecured HTTP traffic to HTTPS.

> Deprecated protocols, weak ciphers, and insecure encryption algorithms are prohibited. These controls support NIST communications protection requirements and HIPAA transmission security standards.

- **3.2.2 Internal Administrative Interfaces:** Administrative web portals, management consoles, cloud dashboards, and privileged web applications shall implement enhanced security controls.

  - Requirements Include:

    - Multi-Factor Authentication (MFA).

    - Role-Based Access Control (RBAC).

    - Unique user accounts.

    - Automatic session timeout after inactivity.

    - Logging of privileged activities.

> Administrative interfaces shall not be accessible from public networks unless protected through approved VPN technologies and MFA. This requirement aligns with CISA Cybersecurity Performance Goals regarding privileged account protection and phishing-resistant authentication.

- **3.3 Vulnerability Management**: All web applications, APIs, and supporting infrastructure shall undergo continuous security assessment to identify, prioritize, and remediate vulnerabilities.

- **3.3.1 Application Security Testing:** All internally developed or custom web applications shall undergo security testing prior to deployment into production environments.

  - Security testing shall:

    - Identify software vulnerabilities and insecure coding practices.

    - Detect known security weaknesses and misconfigurations.

    - Generate reports for remediation and risk tracking.

    - Verify that security controls function as intended.

    - High-risk vulnerabilities identified during testing shall be remediated before production release. This requirement supports CIS vulnerability management objectives.

- **3.3.2 Vulnerability Assessment and Validation:** Web applications shall undergo security assessments within development, testing, or staging environments before deployment.

  - Assessments shall:

    - Evaluate application security controls.

    - Identify authentication and access-control weaknesses.

    - Detect common web application vulnerabilities.

    - Validate security configurations under operational conditions.

    - Security findings shall be documented, prioritized, and remediated according to organizational risk management procedures.

- **3.3.3 Penetration Testing:** External-facing web applications and patient-facing systems shall undergo penetration testing at least annually and after significant architectural procedures.

  - Penetration Testing Shall:

    - Simulate realistic attack scenarios.

    - Assess application security controls.

    - Evaluate authentication and authorization mechanisms.

    - Identify exploitable vulnerabilities.

> Any critical findings shall be addressed through documented corrective action plans and validated through follow-up testing. This requirement aligns with CIS Continuous Vulnerability Management practices and CISA recommendations for reducing exploitable risk.

- **3.3.4 Remediation Requirements:** Vulnerabilities discovered through vulnerability scans, penetration test, SAST, DAST, or security assessments shall be remediated according to the following timeline:

  - Critical Vulnerabilities: Within fourteen (14) calendar days.

  - High Vulnerabilities: Within thirty (30) calendar days.

  - Medium Vulnerabilities: Within sixty (60) calendar days.

  - Low Vulnerabilities: Based upon risk acceptance procedures.

Patch management and vulnerability remediation activities shall follow NIST enterprise patch management guidance and organizational change management procedures.

## Section 4: Email Security Policy (Server and User Controls)

- **4.1 Server-Side Authentication Controls**: All organizational email systems shall implement industry-standard authentication controls to validate message authenticity and reduce domain spoofing risks. NIST and CISA specifically recommend the implementation of Sender Policy Framework (SPF), DomainKeys Identified Mail (DKIM), and Domain-based Message Authentication, Reporting, and Conformance (DMARC) as foundational email security controls.

- **4.1.1 Sender Policy Framework (SPF):** The organization shall maintain correctly configured SPF records for all corporate email domains.

  - Requirements Include:

    - Identification and authorization of approved email sending systems.

    - Removal of obsolete mail servers from SPF records.

    - Regular validation of SPF configurations following infrastructure changes.

    - Monitoring of SPF failures through email security reporting tools.

SPF shall be configured to prevent unauthorized systems from transmitting email on behalf of organizational domains.

- **4.1.2 DomainKeys Identified Mail (DKIM):** All outbound email services shall utilize DKIM cryptographic signing.

  - Requirements include:

    - Cryptographic signing of outbound messages.

    - Secure lifecycle management of DKIM keys.

    - Periodic key rotation procedures.

    - Monitoring of DKIM validation failures.

> DKIM provides message integrity validation and allows recipients to verify that email content has not been altered in transit.

- **4.1.3 Domain-Based Message Authentication, Reporting, and Conformance (DMARC):** All organizational domains used for email communications shall implement DMARC policies.

  - Requirements Include:

    - Deployment of DMARC reporting mechanisms.

    - Monitoring of DMARC Aggregate and forensic reports.

    - Progressive enforcement from monitoring mode to quarantine and reject policies.

    - Investigation of unauthorized sending sources identified through DMARC reporting.

DMARC enables receiving mail systems to quarantine or reject messages that fail SPF and DKIM validation, reducing phishing and domain impersonation attacks. CISA specifically identifies DMARC as an effective control against spoofing and phishing, particularly within healthcare environments.

- **4.1.4 Email Transmission Security:** Email communications contain sensitive organizational information or electronic Protected Health Information (ePHI) shall utilize encrypted transmission methods.

  - Requirements Include:

    - Transport Layer Security (TLS) for mail transfer.

    - Secure certificate validation.

    - Encryption of sensitive email content where appropriate.

    - Compliance with HIPAA transmission security requirements.

> These measures align with NIST Trustworthy Email guidance and HIPAA technical safeguards.

- **4.2 Inbound/Outbound Filtering**: The organization shall deploy layered email filtering controls designed to prevent malicious content, phishing attempts, malware delivery, and unauthorized disclosure of sensitive information.

- **4.2.1 Secure Email Gateway (SEG):** All inbound and outbound email traffic shall be processed through an approved Secure Email Gateway (SEG).

  - The SEG Shall Perform:

    - Spam and phishing detection.

    - Sender reputation analysis.

    - Malware and ransomware screening.

    - Message quarantining.

    - Email authentication validation.

> CISA recommends Secure Email Gateways as a core counter-phishing technology to reduce malicious email delivery to end users.

- **4.2.2 Attachment Sandboxing:** Potentially malicious attachments shall be automatically analyzed before delivery.

  - Requirements include:

    - Sandboxing or detonation chamber technology.

    - Automated behavioral analysis of file activity.

    - Blocking of malicious file types.

    - Quarantining of suspicious content pending administrative review

Attachments identified as malicious shall be blocked and retained for security investigation.

- **4.2.4 Data Loss Prevention (DLP):** Data Loss Prevention technologies shall monitor outbound email communications to prevent unauthorized disclosure of sensitive information.

  - DLP controls shall:

    - Inspect attachments and message content.

    - Detect ePHI, personally identifiable information (PII), and financial data.

    - Generate alerts for unauthorized transmissions.

    - Automatically quarantine high-risk messages when appropriate.

Healthcare-related information transmissions shall comply with HIPAA confidentiality and security requirements.

- **4.2.5 Security Awareness Training:** All employees shall complete annual cybersecurity awareness and phishing identification training. Additional training may be required following significant security incidents, identified security deficiencies, or organizational changes. Training records shall be maintained by the organization and reviewed as part of annual compliance assessments.

- **4.3 SOC Phishing Response Protocol:** The Security Operations Center (SOC) or designated IT security personnel shall maintain procedures for responding to suspected phishing incidents and malicious email activity.

- **4.3.1 Phishing Reporting and Investigation:** Employees shall immediately report suspected phishing emails through approved reporting mechanisms. Security personnel shall review reported messages, analyze message headers, sender authentication results, links, attachments, and indicators of compromise (IOCs), and document investigation findings. User reporting is recognized as a critical component of phishing defense.

- **4.3.2 Containment and Incident Response:** Confirmed malicious emails shall be quarantined or removed from affected mailboxes. Associated IOCs shall be distributed to email security platforms, Endpoint Detection and Response (EDR) systems, antivirus tools, and Security Information and Event Management (SIEM) solutions to prevent further compromise. Significant incidents involving ePHI, patient records, credential theft, or operational disruption shall be escalated and managed according to the organization's Incident Response Plan and applicable HIPAA requirements.

## Section 5: Mobile Device Security Policy

- **5.1 Mobile Device Management (MDM) Architecture**: All organization-owned and authorized personal mobile devices must be enrolled in the organization’s approved Unified Endpoint Management (UEM) platform before accessing organizational resources. Managed devices shall utilize device encryption, multifactor authentication (MFA), compliance monitoring, and remote wipe capabilities to protect electronic Protected Health Information (ePHI). Lost, stolen, or compromised devices must be reported immediately to the Information Technology (IT) Department or Security Operations Center (SOC). Devices used to access Electronic Health Records (EHRs), telehealth services, or other systems containing ePHI shall be subjected to enhanced monitoring and security controls.

- **5.2 Corporate vs. BYOD Standards**: Corporate owned devices shall be configured, managed, and monitored exclusively by the Information Technology (IT) department in accordance with organization security standards. Personally owned devices participating in the Bring Your Own Device (BYOD) program must be enrolled in the approved UEM platform and access organizational resources through Zero Trust Network Access (ZTNA) controls. Organizational data shall remain within secure managed containers, and local storage of ePHI on personal devices is prohibited. BYOD devices shall operate on segregated networks and receive only the minimum access necessary to perform approved business functions.

- **5.3 Application Sandboxing and Compliance**: Only approved and authorized applications may access organizational resources or ePHI. Applications used to access, process, or store patient information shall operate within secure application containers that separate organizational data from personal data. The organization’s UEM platform shall continuously monitor device compliance, including encryption status, operating system updates, malware detection, and unauthorized software installations. Devices determined to be non-compliant, including rooted or jailbroken devices, shall be automatically restricted from organization resources until remediation is completed.

## Section 6: Physical and Facility Security Policy

- **6.1 Perimeter and Zone Defense**: The organization shall maintain a tiered physical security model that restricts facility access based on operational requirements and data sensitivity. Public, administrative, and high-security areas shall be assigned appropriate access controls, with server rooms, data centers, and other critical infrastructure requiring multifactor authentication (MFA), biometric verification, or equivalent security measures. Access to restricted areas shall be granted according to role-based authorization principles, while visitors and contractors shall be escorted and logged. These controls help prevent unauthorized access, theft, tampering, and disruptions to systems containing electronic Protected Health Information (ePHI).

- **6.2 Environmental Monitoring**: The organization shall implement environmental controls to protect critical information systems and healthcare technology from physical threats, including fire, flooding, power outages, and overheating. Data centers, telecommunications rooms, and server facilities shall utilize HVAC systems, environmental monitoring, fire suppression mechanisms, and backup power solutions such as Uninterruptible Power Supplies (UPS). Regular inspections, maintenance, and monitoring shall be conducted to ensure the reliability of systems that support patient care operations and business continuity.

**6.3 Surveillance and Logging**: The organization shall maintain continuous surveillance through CCTV systems, access control technologies, and security logging mechanisms. Surveillance systems shall monitor high-risk locations, including facility entrances, server rooms, and equipment storage areas while access control systems shall record entry attempts, badge usage, visitor activity, and access denials. Physical access privileges shall be reviewed regularly and promptly revoked when no longer required. The Security Operations Center (SOC) shall integrate physical security alerts and logs into centralized monitoring processes to support incident detection, investigations, and the protection of ePHI and critical healthcare systems.

## Section 7: Operational Security Policy

- **7.1 Client Endpoint Security**: All organization workstations, laptops, and clinical devices shall follow approved security configurations established by the Information Technology (IT) Department. Endpoint Detection and Response (EDR), centrally managed firewalls, and regular security updates shall be implemented to protect systems from malicious activity and unauthorized access. Access privileges shall be assigned according to the principle of least privilege, and security logs shall be forward to centralized monitoring systems. Devices used to access Electronic Health Records (EHRs) or other systems containing electronic Protected Health Information (ePHI) shall receive enhanced monitoring and security controls.

- **7.2 Public Kiosks and Shared Systems**: Public kiosks and shared-use systems shall operate in a restricted configuration designed to limit unauthorized access and protect patient information. User sessions shall automatically terminate after periods of inactivity, and locally stored data, browser history, and cached information shall be automatically removed upon logout. Access to administrative functions, removable media, and unauthorized applications shall be restricted. Systems used for patient registration or portal access shall be isolated from critical healthcare infrastructure through network segmentation controls.

- **7.3 Backup and Recovery Operations**: The organization shall maintain secure backup and recovery processes to ensure the availability of critical healthcare systems and patient data. Backups shall be encrypted, stored in geographically separate locations, and protected through immutable storage technologies to reduce the impact of ransomware and other cyber threats. Restoration testing shall be conducted regularly to verify data integrity and recovery capabilities. Because patient care depends on reliable access to clinical information, backup and recovery operations shall be considered mission-critical security functions.

## Section 8: Compliance, Enforcement, and Incident Response

- **8.1 Continuous Monitoring**: The organization shall maintain continuous security monitoring through a centralized Security Information and Event Management (SIEM) system. Security logs generated by network devices, servers, endpoints, mobile devices, and access control systems shall be collected and analyzed by the Security Operations Center (SOC) to identify potential threats, unauthorized access attempts, and policy violations. Monitoring activities shall support regulatory compliance, incident detection, and the protection of electronic Protected Health Information (ePHI).

- **8.2 Non-Compliance Penalties**: All organizational systems and devices shall comply with established cybersecurity standards and security baselines. Devices that fail compliance requirements, including missing security updates, disabled encryption, or unauthorized configurations, may be automatically restricted or isolated from organizational resources until corrective actions are completed. Repeated or intentional violations may result in disciplinary action in accordance with organization policies.

## Section 9: References (APA 7th Edition)

Force, J. T. (2020, December 10). *Security and privacy controls for information systems and organizations*. CSRC. <https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final>

(CMS), C. of M. & M. S. (2007, March). *HIPAA security series compliance deadlines no later than april 20, 2005*. Security Standards: Physical Safeguards. <https://www.hhs.gov/sites/default/files/ocr/privacy/hipaa/administrative/securityrule/physsafeguards.pdf>

(OCR), O. for C. R. (2026, March 19). *The security rule*. HHS.gov. <https://www.hhs.gov/hipaa/for-professionals/security/index.html>

*NIST 800-53 physical and Environmental Protection (PE)*. UpGuard. (n.d.). <https://www.upguard.com/compliance/nist-sp-800-53/pe>

Computer Security Division, I. T. L. (2021, May 4). *Ransomware protection and response: CSRC*. CSRC. <https://csrc.nist.gov/Projects/ransomware-protection-and-response>

*Physical and environmental protection - CSF tools*. CSF Tools - The Cybersecurity Framework for Humans. (2024, December 6). <https://csf.tools/reference/nist-sp-800-53/r5/pe/>

Howell, G., Franklin, J., Sritapan, V., Souppaya, M., & Scarfone, K. (2023, May 17). *Guidelines for managing the security of mobile devices in the enterprise*. CSRC. <https://csrc.nist.gov/pubs/sp/800/124/r2/final>

Electronic Code of Federal Regulations. (n.d.). *45 C.F.R. § 164.310 Physical safeguards.* U.S. Government Publishing Office. <https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-C/section-164.310>

Center for Internet Security. (2024). *CIS Critical Security Controls v8.1*. <https://www.cisecurity.org/controls/v8>

Cybersecurity and Infrastructure Security Agency. (2025). *Cross-sector cybersecurity performance goals (CPGs) 2.0*. <https://www.cisa.gov/cross-sector-cybersecurity-performance-goals/cross-sector-cybersecurity-performance-goals>

Institute of Electrical and Electronics Engineers. (2020). *IEEE Standard for Local and Metropolitan Area Networks: Port-Based Network Access Control (IEEE Std 802.1X-2020).* <https://standards.ieee.org/ieee/802.1X/7345/>

National Institute of Standards and Technology. (2020). *Security and privacy controls for information systems and organizations* (NIST Special Publication 800-53, Rev. 5). U.S. Department of Commerce. <https://doi.org/10.6028/NIST.SP.800-53r5>

Scarfone, K., & Hoffman, P. (2009). *Guidelines on firewalls and firewall policy* (NIST Special Publication 800-41, Rev. 1). National Institute of Standards and Technology. <https://csrc.nist.gov/pubs/sp/800/41/r1/final>

Souppaya, M., & Scarfone, K. (2022). *Guide to enterprise patch management planning: Preventive maintenance for technology* (NIST Special Publication 800-40, Rev. 4). National Institute of Standards and Technology. <https://doi.org/10.6028/NIST.SP.800-40r4>

U.S. Department of Health and Human Services, Office for Civil Rights. (2026). *The Security Rule*. <https://www.hhs.gov/hipaa/for-professionals/security/index.html>

U.S. Government Publishing Office. (2026). *45 CFR § 164.312 Technical safeguards*. Electronic Code of Federal Regulations. <https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-C/section-164.312>

National Institute of Standards and Technology. (2019). *Trustworthy Email (NIST SP 800-177 Rev. 1).* <https://doi.org/10.6028/NIST.SP.800-177r1>

Nightingale, S. (2017). *Email Authentication Mechanisms: DMARC, SPF and DKIM (NIST Technical Note 1945).* <https://doi.org/10.6028/NIST.TN.1945>

Cybersecurity and Infrastructure Security Agency. (2025). *Implement SPF, DKIM, and DMARC Email Authentication Methods.* <https://www.cisa.gov/eviction-strategies-tool/info-countermeasures/CM0055>

Cybersecurity and Infrastructure Security Agency. (2021). *Domain-Based Message Authentication, Reporting and Conformance (DMARC).* <https://www.cisa.gov/sites/default/files/publications/CISA%20DMARC%20HDO_040721_508.pdf>

Cybersecurity and Infrastructure Security Agency. (2023). *Capacity Enhancement Guide: Counter-Phishing Recommendations for Federal Agencies.* <https://www.cisa.gov/resources-tools/resources/capacity-enhancement-guide-federal-agencies-counter-phishing>
