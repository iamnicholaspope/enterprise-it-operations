# Northstar Ridge Solutions, LLC — Business Profile

> **Baseline approval:** The project owner approved this document as the current Phase 00 content baseline on 2026-08-28. Git-backed baseline evidence begins with commit `b52bfc18c728e29fe466fc493958d35e49313909`.

## 1. Document Purpose

This document defines the fictional organization supported by the Enterprise IT Operations Lab. It provides approved business context for later architecture, identity, endpoint, application, service-management, security, automation, monitoring, and recovery work.

It is a business planning document. It does not create accounts, groups, devices, permissions, applications, infrastructure, or final architecture decisions.

## 2. Synthetic-Data Notice

Northstar Ridge Solutions, LLC, its employees, customers, assets, incidents, and all associated business data are entirely synthetic. They exist only for lab, training, testing, demonstration, and portfolio purposes.

No entry in this profile represents a real person, organization, customer, asset, transaction, incident, or operational record. Future lab records must use synthetic data and safe documentation placeholders.

## 3. Company Overview

| Attribute | Approved value |
|---|---|
| Legal-style company name | Northstar Ridge Solutions, LLC |
| Short name | NRS |
| Employees | 26 |
| Primary workplace | One primary office |
| Workforce distribution | 21 office employees and five remote employees |
| IT environment | Hybrid on-premises/cloud |
| IT model | Centralized IT operations supporting office and remote workers |

The company’s industry classification, office location, legal jurisdiction, ownership, customer count, revenue, operating hours, and regulatory obligations are not established.

## 4. Business Model

NRS is a small business-to-business company that provides equipment, implementation, and ongoing support services to business customers.

This model creates business needs for coordinated sales activity, customer support, procurement and inventory work, financial and workforce administration, marketing, secure employee access, reliable business services, and recoverable business information. No specific product catalog, customer record, contract, price, revenue figure, or financial record is defined in this profile.

## 5. Workforce Summary

| Department | Total | Office | Remote |
|---|---:|---:|---:|
| Executive | 3 | 3 | 0 |
| IT | 3 | 3 | 0 |
| Sales | 5 | 3 | 2 |
| Customer Service | 4 | 3 | 1 |
| Finance & HR | 3 | 3 | 0 |
| Operations | 5 | 4 | 1 |
| Marketing | 3 | 2 | 1 |
| **Total** | **26** | **21** | **5** |

## 6. Department Structure

- **Executive:** Organizational leadership and executive coordination.
- **IT:** Centralized IT administration, systems operations, and user support.
- **Sales:** Business-customer acquisition, account activity, and sales coordination.
- **Customer Service:** Ongoing support interactions with business customers.
- **Finance & HR:** Financial and workforce-administration functions whose information requires restricted access.
- **Operations:** Inventory, warehouse, procurement, and operational coordination.
- **Marketing:** Marketing management, digital marketing, and content work.

These descriptions express high-level business functions only. They do not establish detailed workflows, authority limits, or permissions.

## 7. Complete Employee Directory

| Employee ID | Employee | Job title | Department | Work location |
|---|---|---|---|---|
| E001 | Avery Morgan | Chief Executive Officer | Executive | Office |
| E002 | Cameron Reed | Chief Operating Officer | Executive | Office |
| E003 | Riley Parker | Executive Assistant | Executive | Office |
| E004 | Jordan Lee | IT Manager | IT | Office |
| E005 | Taylor Brooks | Systems Administrator | IT | Office |
| E006 | Casey Bennett | Help Desk Technician | IT | Office |
| E007 | Morgan Hayes | Sales Manager | Sales | Office |
| E008 | Ethan Collins | Senior Account Executive | Sales | Remote |
| E009 | Maya Foster | Account Executive | Sales | Office |
| E010 | Lucas Ward | Account Executive | Sales | Remote |
| E011 | Chloe Richardson | Sales Coordinator | Sales | Office |
| E012 | Sophia Turner | Customer Service Manager | Customer Service | Office |
| E013 | Noah Campbell | Support Representative | Customer Service | Office |
| E014 | Grace Mitchell | Support Representative | Customer Service | Remote |
| E015 | Liam Roberts | Support Representative | Customer Service | Office |
| E016 | Natalie Price | Finance & HR Manager | Finance & HR | Office |
| E017 | Owen Stewart | Accountant | Finance & HR | Office |
| E018 | Emma Phillips | HR Coordinator | Finance & HR | Office |
| E019 | Dylan Cooper | Operations Manager | Operations | Office |
| E020 | Hannah Evans | Inventory Coordinator | Operations | Office |
| E021 | Caleb Morris | Warehouse Specialist | Operations | Office |
| E022 | Zoe Peterson | Warehouse Specialist | Operations | Office |
| E023 | Isaac Murphy | Procurement Specialist | Operations | Remote |
| E024 | Lily Carter | Marketing Manager | Marketing | Office |
| E025 | Mason Rivera | Digital Marketing Specialist | Marketing | Remote |
| E026 | Ella Simmons | Content Specialist | Marketing | Office |

## 8. Office vs. Remote Workforce

The 21 office employees work from the single primary office. Office employees generally require managed corporate workstations, although employees with an approved mobility need may use managed laptops.

The five approved remote employees are:

| Employee ID | Employee | Department | Job title |
|---|---|---|---|
| E008 | Ethan Collins | Sales | Senior Account Executive |
| E010 | Lucas Ward | Sales | Account Executive |
| E014 | Grace Mitchell | Customer Service | Support Representative |
| E023 | Isaac Murphy | Operations | Procurement Specialist |
| E025 | Mason Rivera | Marketing | Digital Marketing Specialist |

All five remote employees require managed corporate laptops and secure access to only the resources appropriate to their roles. Their specific connectivity method, endpoint configuration, and access entitlements remain future architecture decisions.

## 9. Role Descriptions

Role descriptions are limited to planning-level business responsibilities inferred from the approved titles:

- **Executive roles:** Organizational leadership, operational oversight, and executive coordination.
- **IT Manager:** IT service and operations leadership, prioritization, and appropriate administrative oversight.
- **Systems Administrator:** Appropriate systems administration and infrastructure support.
- **Help Desk Technician:** Front-line employee support and initial incident/request handling.
- **Sales roles:** Customer and prospect relationship activity, sales coordination, and appropriate CRM use.
- **Customer Service roles:** Customer support activity and appropriate access to customer-service information.
- **Finance & HR roles:** Financial and workforce administration with restricted information access.
- **Operations roles:** Inventory, warehouse, procurement, and related operational activity.
- **Marketing roles:** Marketing planning, digital marketing, and content activity.

These descriptions do not grant permissions or establish a final separation-of-duties model.

## 10. Management Structure

The approved dataset identifies the following management or leadership titles:

- Avery Morgan — Chief Executive Officer
- Cameron Reed — Chief Operating Officer
- Jordan Lee — IT Manager
- Morgan Hayes — Sales Manager
- Sophia Turner — Customer Service Manager
- Natalie Price — Finance & HR Manager
- Dylan Cooper — Operations Manager
- Lily Carter — Marketing Manager

Formal reporting relationships, delegation authority, approval thresholds, and succession arrangements have not been approved. A later access-control and workflow design may use managerial roles for review or approval, but it must not infer unrestricted access from title alone.

## 11. IT Operating Model

NRS uses a centralized IT operating model supported by three office-based IT employees. IT is expected to provide appropriate systems administration, employee support, identity and access administration, endpoint operations, monitoring, service-management administration, change control, asset tracking, security operations, and recovery coordination as those capabilities are introduced through the master roadmap.

Administrative access must be appropriate to job role. Everyday user identities must not automatically receive unrestricted privileged access. Separate privileged administrative identities should be considered during later identity architecture. This profile does not assign administrative roles or finalize an operating-hours, escalation, on-call, or support-tier model.

## 12. Identity Conventions

The following are planning conventions, not final identity architecture:

| Attribute | Example |
|---|---|
| Display name | Avery Morgan |
| Username | `avery.morgan` |
| Documentation/example email | `avery.morgan@example.invalid` |
| Employee ID | `E001` |

The lowercase `first.last` username pattern is a preliminary convention. Collision handling, name changes, aliases, service accounts, privileged identities, and lifecycle rules must be designed later. `example.invalid` is reserved here as a safe documentation placeholder; it is not a permanent Active Directory domain, UPN suffix, public domain, or production email domain.

Candidate logical access groups are:

- `GG-Executive-Users`
- `GG-IT-Users`
- `GG-Sales-Users`
- `GG-CustomerService-Users`
- `GG-FinanceHR-Users`
- `GG-Operations-Users`
- `GG-Marketing-Users`
- `GG-Remote-Users`
- `GG-VPN-Users`
- `GG-CRM-Users`
- `GG-ServiceNow-Users`

These groups are not implemented and are not the final RBAC design. Later identity design should separate role and resource access where appropriate, apply least privilege, and assign permissions through groups rather than directly to individual users.

## 13. Preliminary Access Requirements

### CRM

- Sales requires CRM access.
- Selected Customer Service users may require CRM access.
- Marketing may require access appropriate to approved work.
- Appropriate management roles may require reporting or oversight access.

### Service Management

- Employees should be able to submit incidents and requests.
- IT administers ITSM capabilities.
- Managers may later participate in approvals.
- ITAM and CMDB roles will be designed later.

### Finance & HR

- Finance and HR information must be restricted.
- Least privilege is required.
- Appropriate management access remains to be determined.

### Operations

- Operations requires access to inventory- and procurement-related resources.
- Appropriate management access may be required.

### IT

- IT requires administrative capabilities appropriate to each job role.
- Everyday identities must not automatically receive unrestricted privileged access.
- Separate privileged administrative identities should be evaluated during identity architecture.

This section is not a final access-control matrix. Specific users, entitlements, approval paths, role/resource groups, privileged roles, and segregation-of-duties rules remain open.

## 14. Endpoint Requirements

- Office employees generally use managed corporate workstations.
- Employees with an approved mobility requirement may use managed laptops.
- All five remote employees require managed corporate laptops.
- Corporate endpoints should support centralized identity, security configuration, compliance assessment, software management, support, inventory tracking, and lost-device response where project capabilities and licensing permit.

Preliminary naming examples are:

- `WKS-EXEC-001`
- `WKS-IT-001`
- `WKS-SALES-001`
- `WKS-FIN-001`
- `LTP-SALES-001`
- `LTP-CS-001`
- `LTP-OPS-001`
- `LTP-MKT-001`

These examples do not reserve or assign devices. No final inventory, hardware model, serial number, operating-system edition, license, IP address, device ID, or individual office-device assignment is established here.

## 15. Remote-Work Requirements

The five remote employees need secure, logged access to authorized corporate resources from managed corporate laptops. Remote access must:

- authenticate the employee through approved identity controls;
- limit access according to role and resource need;
- deny unauthorized access;
- support account disablement and access revocation;
- use endpoint compliance and MFA where available and appropriate;
- support corporate DNS and internal-resource access as designed;
- generate useful operational and security logs; and
- support incident response for lost, compromised, or non-compliant devices.

The firewall platform, VPN product, authentication integration, public endpoint, network addressing, and detailed remote-access policy are not selected by this profile.

## 16. Business Applications

- **CRM:** Supports business-customer relationship and sales activity. It is expected to support the lead-to-sale model established by the roadmap. No customer records are created here.
- **ServiceNow capabilities:** Support employee incidents and requests and later ITSM, ITAM, CMDB, change, knowledge, approval, and service-catalog workflows where eligible.
- **Finance and HR resources:** Support financial and workforce administration and require restricted, least-privilege access. No specific application or dataset is selected.
- **Operations resources:** Support inventory and procurement activity. No specific application or inventory dataset is selected.
- **File services:** Support controlled shared business information where later requirements and architecture define them.
- **Microsoft cloud services:** May support identity, productivity, and endpoint management where eligibility and licensing permit.
- **Lab email:** Supports internal learning and testing of enterprise email protocols; it is not established as the production business email platform.

## 17. Business Services

The business depends at a high level on:

- identity and authentication;
- name resolution;
- network and firewall connectivity;
- secure remote access;
- customer-facing business services;
- customer relationship management;
- finance and HR information;
- file services;
- service management;
- monitoring and alerting;
- inventory and procurement resources;
- marketing systems; and
- internal lab email capabilities.

The exact catalog, ownership, service boundaries, dependencies, and CMDB relationships will be defined later.

## 18. Preliminary Service Criticality

These are preliminary classifications for planning only:

| Classification | Business services |
|---|---|
| Critical | Identity/authentication; DNS; network/firewall |
| High | Remote access; customer-facing business services; CRM; finance data; file services |
| Medium/High | ServiceNow; monitoring/alerting |
| Medium | Marketing systems; lab email |

These classifications do not establish RPO, RTO, SLA, retention, uptime, support-hours, or outage-tolerance values. Those require later business-continuity and disaster-recovery decisions.

## 19. Data Sensitivity Considerations

NRS will use synthetic data in the lab. Even synthetic records should model appropriate handling boundaries:

- Finance and HR information should be treated as restricted.
- Identity, authentication, security, and privileged-administration information should be tightly controlled.
- Customer relationship, support, inventory, procurement, asset, and configuration information should be available only to appropriate roles.
- Public marketing material may require fewer restrictions than internal business information, but publication authority is not defined here.
- Passwords, secrets, tokens, private keys, and real personal or business data must not appear in source control, screenshots, exports, or evidence.

A formal data-classification scheme, retention schedule, privacy policy, and regulatory mapping remain future decisions.

## 20. Security Expectations

- Use centralized identity and least privilege.
- Prefer role- and resource-based group assignments over direct user permissions.
- Separate everyday and privileged administrative identities where later design confirms the approach.
- Apply MFA, RBAC, endpoint compliance, segmentation, secure defaults, logging, and controlled administrative access where supported.
- Prevent direct Internet exposure of domain controllers and internal management interfaces.
- Keep insecure lab email protocols from public exposure.
- Support account disablement, remote-device response, access review, and auditability.
- Use only synthetic data and sanitized evidence.

This profile does not define a regulatory framework or finalize specific security products or policies.

## 21. Employee Onboarding

At a business level, onboarding should:

1. begin from an approved employment and start-date request;
2. identify the employee, department, job role, work location, manager/approver, and required resources;
3. create appropriate identity and access through approved workflows;
4. assign and record a managed endpoint and other approved assets;
5. provide role-appropriate application and remote access;
6. communicate initial access securely;
7. validate that required access works and excess access is absent; and
8. retain approval, completion, and asset evidence.

The process must be understood and documented manually before Phase 16 automation. This profile does not onboard any employee or define final approvers and entitlements.

## 22. Employee Offboarding

At a business level, offboarding should:

1. begin from an authorized termination or separation request;
2. establish the effective time and responsible approver;
3. disable or revoke identity, remote access, sessions, privileged access, and application access as appropriate;
4. recover or account for assigned assets;
5. preserve or transfer business information according to later-approved policy;
6. update asset, service-management, and access records;
7. verify that access has been removed; and
8. retain approval and completion evidence.

No retention period, mailbox/data handling rule, legal hold, or deletion schedule is established.

## 23. Incident/Request Workflow Expectations

- Employees should be able to report incidents and submit service requests through an established channel.
- Records should capture the affected user or service, business impact, description, status, ownership, actions, resolution, and relevant evidence.
- IT should triage, prioritize, investigate, communicate, resolve, and close work using documented procedures.
- Repeated incidents may lead to problem investigation; controlled remediation may require a change record.
- Managers may participate in approvals where later workflow design requires it.
- Security events, lost devices, outages, and access failures should follow appropriate escalation and evidence handling.

ServiceNow is established later in the roadmap; no instance, workflow, priority matrix, SLA, or approval chain is configured here.

## 24. Asset-Management Expectations

- Track company-managed endpoints, servers, network equipment, mobile devices where applicable, applications, and software/license information.
- Associate assets with an appropriate lifecycle state, custodian or user where relevant, business purpose, and supporting records.
- Record assignment, return, loss, replacement, retirement, and disposal events when those processes are defined.
- Keep ITAM records and CMDB configuration relationships distinct but appropriately connected.
- Ensure remote laptops and privileged or critical infrastructure receive appropriate tracking.

This profile does not create the final asset inventory or assign models, serial numbers, licenses, addresses, or device identifiers.

## 25. Monitoring Expectations

- Monitor the health and availability of critical infrastructure, servers, applications, containers, network/firewall services where practical, and other documented critical services.
- Route actionable alerts to an appropriate notification path and later to service-management workflows where designed.
- Test alerts using safe service interruptions or thresholds.
- Retain useful logs and evidence without exposing secrets or sensitive data.
- Align monitoring priority with the preliminary service-criticality classifications until formal service targets exist.

No alert threshold, retention duration, on-call schedule, or SLA is established here.

## 26. Backup/Recovery Expectations

- Identify critical systems and information requiring protection.
- Define RPO, RTO, retention, frequency, location, and recovery priority during later continuity and DR planning.
- Use appropriate free/community or native backup methods where practical.
- Protect identity, CRM/database, file, configuration, and monitoring information as later designs require.
- Test recovery, including deleted files, CRM/database, failed VMs, domain-controller failure, configuration, and monitoring-system recovery.
- Record recovery results, gaps, and corrective actions.

A backup is not considered valid until a restore is tested. This profile does not set numeric recovery or retention targets.

## 27. Example Operational Scenarios

The following are future lab and testing scenarios, not completed work:

1. Ethan Collins or Lucas Ward cannot connect remotely to authorized corporate resources.
2. Grace Mitchell loses a managed corporate laptop.
3. A future synthetic Sales employee requires onboarding.
4. A synthetic employee termination requires complete and timely access revocation.
5. A critical server or service becomes unavailable.
6. The synthetic CRM database requires recovery.
7. Unauthorized or suspicious authentication is detected.
8. A non-compliant endpoint attempts to access corporate resources.

Scenario use must not imply that an incident occurred or a control passed until a documented test is performed and evidence is recorded.

## 28. Known Assumptions

- Department descriptions and role summaries are planning-level interpretations of the approved department names, job titles, and business model.
- Manager titles identify likely workflow participants, but formal reporting relationships and approval authority are not established.
- Centralized IT responsibilities will be distributed among the three IT roles during later operating-model and access design.
- Office employees generally use corporate workstations; specific mobility needs and device assignments remain undecided.
- Synthetic test users may represent future hires or departures when a scenario requires a person not listed in the current directory.
- Preliminary service criticality will guide planning until formal business-continuity analysis is approved.

## 29. Open Business Decisions

- Formal reporting relationships and approval authority
- Named project sponsor/project owner
- Office location, legal jurisdiction, industry classification, and operating hours
- Detailed product/service catalog and customer-facing service boundaries
- Department workflows and separation-of-duties requirements
- Final identity naming, collision, alias, privileged-account, and lifecycle rules
- Permanent AD domain, UPN suffix, public domain, and production email domain
- Final RBAC model, access-control matrix, group design, and access-review cadence
- Exact endpoint mix, mobility approvals, device assignments, platform standards, and lifecycle rules
- Remote-access product, authentication design, and detailed policy
- Application selections and exact user entitlements where not already governed
- Formal data classification, retention, privacy, and disposal rules
- Incident priorities, escalation paths, approval workflows, support hours, and SLAs
- Asset ownership, inventory fields, procurement, return, retirement, and disposal processes
- Monitoring thresholds, notification ownership, log retention, and response expectations
- RPO, RTO, backup retention, frequency, location, recovery order, and outage tolerance
- Available licensing, developer/evaluation eligibility, and any approved paid spending

## 30. Relationship to Project Requirements

| Requirement | Business-profile relationship |
|---|---|
| `REQ-001` | All 26 employees need role-appropriate centralized identity and authentication. |
| `REQ-002` | Critical identity and DNS services require the roadmap’s redundant domain-controller design and failure validation. |
| `REQ-003` | Five identified remote employees require secure access to authorized resources. |
| `REQ-004` | Preliminary service priorities identify infrastructure and applications requiring health monitoring and alerting. |
| `REQ-005` | Managed endpoints, especially five remote laptops, require lost-device and non-compliance response where supported. |
| `REQ-006` | Corporate devices, infrastructure, applications, and licenses require controlled asset tracking. |
| `REQ-007` | Employees need incident/request submission, while IT needs incident, problem, change, and request workflows. |
| `REQ-008` | Critical identity, CRM, file, configuration, and monitoring capabilities require tested recovery. |
| `REQ-009` | Onboarding is defined at business level so appropriate steps may later be automated. |
| `REQ-010` | Business and IT changes require documented, testable, evidence-backed control. |
| `REQ-011` | Later architecture changes supporting these business needs must be documented in PlantUML. |
| `REQ-012` | Approved cloud resources should use controlled, repeatable IaC where practical. |

This mapping provides business context. The requirements traceability matrix remains a separate Phase 00 deliverable.
