# Project Charter

> **Baseline approval:** The project owner approved this document as the current Phase 00 content baseline on 2026-08-28. Its task remains `[~]` until all applicable Definition of Done evidence, including Git-backed change history, is available.

## 1. Executive Summary

This project will design, build, validate, and document a realistic hybrid IT environment for Northstar Ridge Solutions, LLC (NRS), a synthetic 26-employee small business with 21 office employees, five remote employees, and one primary office. NRS provides equipment, implementation, and ongoing support services to business customers. The environment will support centralized IT operations, secure access for office and remote workers, resilient identity services, managed endpoints, business applications, monitoring, service management, automation, and recoverability.

The project is governed by documented business requirements and will be delivered incrementally. Technology will be introduced only when it supports an established business or operational need. Installation alone will not constitute completion; applicable architecture, configuration, integration, testing, failure testing, troubleshooting, evidence, and documentation must also be completed.

## 2. Business Scenario

The modeled organization is Northstar Ridge Solutions, LLC (NRS), a small B2B company providing equipment, implementation, and ongoing support services to business customers. It has:

- 26 employees in total;
- 21 employees who work from one primary office;
- five remote employees;
- a hybrid on-premises/cloud IT environment;
- centralized IT operations; and
- a need to support a secure remote workforce; and
- Executive, IT, Sales, Customer Service, Finance & HR, Operations, and Marketing departments.

The authoritative department totals, employee directory, work locations, and planning-level business conventions are maintained in `docs/business-profile.md` and are not duplicated in this charter.

NRS and every company identity, employee, customer, asset, incident, item of financial information, and other business record used by this project are entirely synthetic lab data. They exist only for lab, training, testing, demonstration, and portfolio purposes and do not represent real people, organizations, customers, property, events, or transactions.

The company's industry classification, legal jurisdiction, office location, formal reporting relationships, and detailed business processes remain unspecified.

## 3. Business Need / Problem Statement

The organization needs a coherent and supportable IT operating environment rather than disconnected systems. Employees need reliable identity and access, remote personnel need secure access to appropriate corporate resources, and IT needs the ability to manage endpoints, services, assets, incidents, changes, monitoring, and recovery from a central operating model.

Without documented architecture, redundancy, security controls, operational processes, monitoring, and tested recovery, the organization would face avoidable risks including service disruption, inconsistent access, unmanaged devices, limited operational visibility, weak change control, and unverified recoverability.

## 4. Project Purpose

The project will create a realistic enterprise-style IT environment scaled to the needs and constraints of a 26-employee business. It will demonstrate that business requirements can be translated into architecture, controlled implementation, secure configuration, integration, validation, evidence, and sustainable operating documentation.

The resulting lab will also provide truthful, reviewable evidence of hands-on IT capability. Learning value is a project benefit, but it does not independently justify a technology choice.

## 5. Project Scope

The project includes:

- governance, requirements, risks, decisions, traceability, tasks, testing, evidence, and operating documentation;
- virtualization and segmented network foundations;
- centralized identity with redundant domain controllers and DNS services;
- managed Windows clients, DHCP, and Group Policy;
- Linux and container foundations;
- centralized monitoring, logging, alerting, and failure detection;
- IT service, asset, configuration, request, change, problem, incident, and knowledge-management capabilities;
- a representative customer relationship management application and an internal email protocol lab;
- eligible Microsoft cloud identity and endpoint-management capabilities;
- secure access and supporting controls for five remote employees;
- layered security operations and validation exercises;
- backup, restore, and disaster-recovery planning and testing;
- automation of processes that are first understood and documented manually;
- approved cloud and Infrastructure as Code work with cost controls;
- CI/CD where it improves an established workflow; and
- optional application-delivery work and later Kubernetes work only when their documented prerequisites and constraints are satisfied.

All work remains subject to the authoritative sequence and dependencies in `docs/master-build-roadmap.md`.

## 6. Explicit Out-of-Scope Items

The following are outside the current project scope unless separately documented and approved:

- production deployment for a real organization;
- use of real employee, customer, financial, or regulated data;
- invention or simulation of industry-specific regulatory compliance without an established business requirement;
- direct Internet exposure of domain controllers or internal management interfaces;
- insecure public exposure of lab SMTP, IMAP, or POP3 services;
- paid cloud infrastructure or paid production licensing without explicit approval;
- final selection of products, services, or addressing before the relevant architecture decision phase;
- implementation of later phases before their dependencies are complete;
- unsupported claims that a technology is production-ready or résumé-ready based only on installation; and
- commitments to production service levels, availability targets, recovery targets, or staffing levels that have not been approved.

## 7. Business Objectives

- Provide employees with consistent access to authorized business resources through centralized identity.
- Support secure and practical access for five remote employees.
- Reduce avoidable service interruption through identity redundancy, monitoring, controlled change, and tested recovery.
- Give IT a centralized way to manage incidents, problems, changes, requests, knowledge, assets, and configuration relationships.
- Improve accountability by making architecture, changes, tests, results, risks, and evidence traceable.
- Support employee onboarding and other repeatable processes with automation where it is practical and controlled.
- Keep the environment financially appropriate for a small business by preferring free or low-cost options.

## 8. Technical Objectives

- Implement centralized identity and redundant Active Directory domain controllers, including DNS redundancy, replication, failover, FSMO awareness, troubleshooting, and recovery.
- Establish segmented, controlled network access for management, office users, servers, guests, infrastructure devices, and remote connectivity after designs are approved.
- Manage supported endpoints and enforce appropriate identity, compliance, access, and security policies where licensing permits.
- Monitor server, application, container, and network health where practical and verify alert delivery through controlled failure tests.
- Establish service management, asset management, and configuration-management capabilities appropriate to the modeled business.
- Protect critical systems with documented backups and successful restore tests.
- Use documented, testable automation and APIs where they improve an understood process.
- Provision approved cloud resources reproducibly with Infrastructure as Code where practical and cost-controlled.
- Maintain architecture in PlantUML and record significant choices in Architecture Decision Records.

Product and design choices that the project sources identify as proposed, optional, conditional, or licensing-dependent remain open until their designated phase.

## 9. Success Criteria

The project will be successful when:

- employees can authenticate through centralized identity (`REQ-001`);
- two domain controllers provide validated AD and DNS redundancy, authentication failover, replication, and recovery (`REQ-002`);
- remote employees can securely access authorized corporate resources and unauthorized access is denied (`REQ-003`);
- IT can monitor server and application health and verify alert paths through testing (`REQ-004`);
- supported managed-device loss and non-compliance scenarios can be controlled where licensing and lab capabilities permit (`REQ-005`);
- hardware and software assets can be tracked (`REQ-006`);
- incidents, problems, changes, and requests can be managed through documented workflows (`REQ-007`);
- critical systems have documented backups and successful recovery tests (`REQ-008`);
- approved onboarding steps are automated where practical after the manual process is understood (`REQ-009`);
- infrastructure changes are documented, testable, and supported by evidence (`REQ-010`);
- architecture is maintained in PlantUML (`REQ-011`);
- approved cloud resources use Infrastructure as Code where practical (`REQ-012`); and
- applicable task Definition of Done and phase or milestone completion criteria are satisfied.

## 10. Major Project Deliverables

- Project governance set: charter, context, requirements, roadmap, plan, tasks, risks, traceability, and ADRs.
- PlantUML architecture library and approved system/network designs.
- Virtualization, network, firewall, and secure remote-access foundation.
- Redundant Windows identity, DNS, DHCP, Group Policy, and managed-client environment.
- Linux, Docker, and Docker Compose foundation.
- Centralized observability platform.
- ITSM, ITAM, CMDB, service catalog, and knowledge-management capability.
- Representative CRM and internal email protocol lab.
- Eligible Microsoft cloud identity and endpoint-management configuration.
- Layered security controls and documented security exercises.
- Backup, restore, and disaster-recovery capability with recorded tests.
- Approved PowerShell, Python, API, IaC, and CI/CD artifacts.
- Conditional application-delivery lab and later Kubernetes lab when justified and eligible.
- Testing records, sanitized evidence, runbooks, change records, incident records, and troubleshooting documentation.

## 11. Stakeholders

Although the synthetic employee directory is established in `docs/business-profile.md`, the project sponsor, formal reporting relationships, and approval authority are not. Charter stakeholders therefore remain expressed as roles:

- Business sponsor or project owner
- Business leadership
- IT owner/administrator
- Office employees
- Remote employees
- Managers or process owners affected by access, onboarding, service requests, assets, CRM, and recovery
- Security, privacy, or risk reviewer where such responsibility exists
- Technology and service providers whose licensing or developer environments are used

## 12. Roles and Assumed Responsibilities

The following role allocation is an operating assumption for this simulated project and does not establish actual company staffing:

| Role | Assumed responsibility |
|---|---|
| Business sponsor/project owner | Approves the charter, priorities, scope changes, costs, major risks, and final acceptance. |
| IT owner/administrator | Designs, implements, secures, tests, troubleshoots, documents, and operates the lab within approved scope. |
| Business/process owner | Clarifies business workflows and validates that a service or application supports its intended outcome. |
| Security/risk reviewer | Reviews exposure, access, secrets, licensing, recovery, and risk treatment when applicable. |
| Employees/test users | Participate in controlled acceptance scenarios and report access or usability issues using synthetic lab data. |

One person may perform multiple roles in the lab, but approvals and evidence should identify which role was being exercised.

## 13. Constraints

- The environment represents a small business and should remain proportionate to 26 employees.
- The project must follow the phase order and dependencies in `docs/master-build-roadmap.md`.
- Infrastructure cannot be considered complete based solely on installation.
- Unfinished or insecure services must not be exposed publicly.
- Architecture decisions must be documented before dependent implementation proceeds.
- The project uses synthetic information and sanitized evidence rather than real sensitive data.
- Access to developer programs, trials, evaluation media, hardware capacity, and cloud services may limit implementation depth.

## 14. Budget Constraints

- No dollar budget is established.
- Free, open-source, community, developer, evaluation, or otherwise low-cost options are preferred where practical.
- Paid cloud resources and paid production licenses require explicit approval before commitment or creation.
- Cost awareness, budgets, alerts, and cleanup procedures must precede approved Azure deployment.
- A lower-cost option must still satisfy the applicable business, security, testing, and support requirements.

## 15. Licensing Constraints

Licensing must be recorded accurately and classified as one of the following where relevant:

- free/open source;
- free developer use;
- time-limited evaluation or trial; or
- paid production license.

Developer, evaluation, and trial rights must not be represented as permanent production entitlements. Features dependent on Microsoft, ServiceNow, Citrix, cloud, or other vendor eligibility may be implemented only when suitable access exists. Conditional work may be documented conceptually when hands-on use is unavailable, but it must not be represented as implemented or validated.

## 16. Security Constraints

- Passwords, API keys, access tokens, private keys, production secrets, and unsanitized credentials must not be committed or included in evidence.
- Domain controllers and internal management interfaces must never be directly exposed to the Internet.
- Lab mail services must remain internal until a documented design and security review supports any public exposure; insecure SMTP/POP3 exposure is prohibited.
- Least privilege, RBAC, MFA, segmentation, secure defaults, logging, and controlled administrative access must be applied where appropriate and supported.
- Public services require deliberate DNS, TLS, firewall, and exposure decisions.
- Real personal, customer, financial, or regulated data is not required and must not be introduced for realism.

## 17. High-Level Risks

| Risk | Potential effect | Initial response |
|---|---|---|
| Limited hardware or lab capacity | Reduced scale, performance, or concurrent system availability | Size systems proportionately, document limitations, and sequence resource-intensive work. |
| Trial, evaluation, or developer access expires or is unavailable | Some planned capabilities cannot be implemented or retested | Record licensing class and expiry constraints; use approved alternatives or document the limitation. |
| Uncontrolled cloud or licensing cost | Unexpected expense | Require approval, budgets, alerts, cleanup procedures, and low-cost defaults. |
| Premature or insecure public exposure | Unauthorized access or compromise | Keep unfinished systems private and require a documented security review before exposure. |
| Single points of failure | Authentication or service outages | Implement planned redundancy, monitoring, backup, and recovery testing. |
| Scope expansion for learning alone | Delayed delivery and disconnected technology demonstrations | Require requirement traceability and documented justification for additions. |
| Missing or weak evidence | Work cannot be validated or represented truthfully | Define tests before completion and retain sanitized results. |
| Configuration drift or undocumented change | Inconsistent systems and difficult recovery | Use change records, documentation, automation, IaC, and repeatable validation where practical. |
| Accidental disclosure of secrets | Security compromise | Sanitize outputs, use secure secret handling, and review artifacts before retention. |
| Overstated lab capability | Incorrect business or résumé claims | Distinguish designed, implemented, tested, and conceptual work. |

These risks are high-level charter inputs and do not replace the Phase 00 risk register.

## 18. Dependencies

- Project Governance must establish requirements, controls, documentation structures, and traceability before infrastructure deployment.
- Virtualization and the network/firewall foundation precede server and service deployment.
- DC01 precedes DC02 and Active Directory replication.
- DHCP, Group Policy, and Windows clients depend on the identity and network foundations.
- Linux precedes Docker; Docker precedes container-dependent workloads and Kubernetes.
- Core observability precedes the addition of many business applications.
- ServiceNow precedes its later operational integrations; CRM and email precede dependent integrations and automation.
- Microsoft cloud identity precedes Intune-dependent and cloud-identity-dependent controls.
- Remote-workforce controls depend on appropriate network, identity, and endpoint foundations.
- Security operations and backup/recovery build on previously deployed services.
- Automation follows documented manual processes.
- Azure/IaC follows cost-control planning; CI/CD follows established engineering workflows.
- Citrix/application delivery is optional and licensing-dependent.
- Kubernetes requires the prerequisites stated in the master roadmap.

Milestone 1 is not complete until identity and DNS continue during a planned DC01 outage, DC02 provides authentication and DNS failover, DC01 is restored, and recovery is documented.

## 19. Documentation Standards

- `docs/master-build-roadmap.md` governs phase numbering, order, dependencies, milestones, and completion criteria.
- `docs/tasks.md` records implementation status.
- Requirements retain stable IDs and trace through architecture, implementation, testing, and evidence.
- PlantUML is the required architecture diagram format; significant decisions are recorded as ADRs.
- Material changes update relevant architecture, configuration notes, tests, evidence, runbooks, task status, and traceability.
- Operational documentation may include runbooks, troubleshooting guides, knowledge articles, change records, and incident records.
- Documentation must distinguish proposals, approved decisions, implemented state, test results, and future work.

## 20. Evidence Standards

- Evidence must be attributable to a requirement, task, change, or test.
- Acceptable evidence may include sanitized screenshots, command output, logs, configuration exports, diagrams, dashboard images, ServiceNow records, scripts, and test results.
- Evidence must show meaningful configuration, integration, troubleshooting, testing, automation where appropriate, and documentation—not merely installation.
- Evidence must not contain secrets, private keys, access tokens, passwords, real sensitive data, or unnecessary identifying information.
- Conceptual work, simulated exercises, passed tests, failed tests, and remediated results must be labeled accurately.

## 21. Testing Expectations

Applicable test records must include:

- a test ID;
- objective;
- prerequisites;
- procedure;
- expected result;
- actual result; and
- PASS/FAIL status.

Testing must cover normal operation, access restrictions, integration, and controlled failure or recovery scenarios where appropriate. Failed tests must be retained or summarized with diagnosis, corrective action, and retest results. A backup is not valid until a restore is tested, and redundant identity is not validated until failover and recovery are exercised.

## 22. Approval Criteria

The charter is ready for approval when:

- it matches the established 26-employee business scenario;
- its purpose and scope are business-focused and traceable to the requirements register;
- exclusions, constraints, risks, dependencies, documentation, evidence, and testing expectations are explicit;
- it does not silently finalize proposed or conditional architecture choices;
- assumptions and unresolved questions are visible; and
- the business sponsor/project owner accepts the charter as the governing scope baseline.

Approval of this charter does not approve paid spending, public exposure, a specific product, or implementation of a future phase.

## 23. Project Completion Criteria

The overall project is complete only when:

- approved in-scope phases and milestones satisfy their authoritative completion criteria;
- applicable requirements are implemented or formally dispositioned, validated, and traceable to evidence;
- configurations, security considerations, integrations, tests, failure exercises, and recovery results are documented;
- current PlantUML diagrams and ADRs reflect material architecture and design decisions;
- applicable runbooks, troubleshooting guidance, change records, incident records, and knowledge are available;
- backups and recovery procedures for critical systems have passed documented tests;
- no unresolved critical defect or risk prevents the modeled business from using the validated capabilities;
- no secrets or real sensitive business data are included in project artifacts;
- licensing and cost classifications are accurate; and
- the business sponsor/project owner provides final acceptance.

Completion may exclude explicitly optional or unavailable capabilities when their exclusion is documented, approved, and does not prevent satisfaction of a mandatory requirement.

## Assumptions and Open Questions

### Assumptions

- The environment is a controlled lab representing a hypothetical organization, not a production deployment.
- Role-based charter stakeholders are sufficient until a project sponsor, formal reporting relationships, and approval authority are established.
- One person may perform multiple project roles, provided the role exercised is identified in approvals and evidence.
- Synthetic users and data will be used for implementation and testing.
- The business needs described in the requirements register are approved planning inputs, even though most remain in Planned status.
- Optional or licensing-dependent scope may be omitted with documented approval when mandatory requirements remain satisfied.

### Open Questions

- Who will act as business sponsor/project owner and provide charter approval?
- What industry classification, legal jurisdiction, office location, formal reporting relationships, approval authority, and detailed business processes should be established?
- What hardware capacity, operating limits, and acceptable lab availability exist?
- What budget approval process applies when a free option is insufficient?
- Which developer, trial, evaluation, and paid licenses are available, and when do they expire?
- What service priorities, recovery objectives, retention periods, and acceptable outage targets should be approved?
- Which proposed network, firewall, VPN, cloud, endpoint, application-delivery, and optional security choices will be selected in their designated phases?
