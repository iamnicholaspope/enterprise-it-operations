# Requirements Traceability Matrix

> **Baseline approval:** The project owner approved this document as the current Phase 00 traceability baseline on 2026-08-28. Git-backed baseline evidence begins with commit `b52bfc18c728e29fe466fc493958d35e49313909`.

## Purpose

This Requirements Traceability Matrix (RTM) maps every approved requirement in `docs/requirements.md` to its supported business need, architecture, roadmap phase, implementation tasks, risks, future testing, evidence, operational documentation, and validation state.

The traceability model is:

``` text
Requirement
    ↓
Business Need
    ↓
Architecture / ADR
    ↓
Implementation Phase
    ↓
Implementation Task
    ↓
Test
    ↓
Evidence
    ↓
Operational Documentation
    ↓
Requirement Validation
```

The matrix deliberately exposes missing artifacts. `TBD`, `None yet`, and `Not yet captured` mean that the referenced work does not currently exist; they are not artifact identifiers.

## Status Definitions

### Implementation Status

- **Not Started:** Required implementation has not begun.
- **In Progress:** Some applicable implementation or architecture work exists, but the requirement is not fully implemented.
- **Implemented:** Applicable implementation work is complete, but validation is tracked separately.
- **Blocked:** Implementation cannot proceed because of a documented blocker.
- **Not Applicable:** The requirement does not apply under an approved scope decision.

### Validation Status

- **Not Validated:** Required testing and evidence have not established satisfaction.
- **Partially Validated:** Some required tests/evidence passed, but validation is incomplete.
- **Validated:** Traceable implementation, applicable testing, and evidence demonstrate that the requirement is satisfied.
- **Failed:** Testing or evidence demonstrates that the requirement is not satisfied.

An implementation task marked `[x]` does not by itself validate a requirement. Validation requires traceable implementation, testing, and evidence where applicable.

## Requirement Traceability

### REQ-001

- **Requirement ID:** `REQ-001`
- **Requirement summary:** Employees must authenticate through centralized identity
- **Business rationale / business need:** All 26 NRS employees require consistent, role-appropriate authentication to approved business resources; onboarding, offboarding, remote access, and access control depend on a centrally governed identity lifecycle.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §9 and `docs/business-profile.md` §§12, 20–22, and 30.
- **Related project phase(s):** Phase 02 — Windows Server / DC01; Phase 03 — DC02 & Active Directory Replication; Phase 04 — DHCP, Group Policy & Windows Clients; Phase 11 — Microsoft Cloud Identity; Phase 14 — Security Operations; Phase 16 — Automation.
- **Related architecture diagram(s):** `architecture/diagrams/01-overview/01-enterprise-overview.puml`; `architecture/diagrams/03-identity/01-ad-replication.puml`; `architecture/diagrams/05-cloud/01-hybrid-cloud.puml`; `architecture/diagrams/06-security/01-security-controls.puml`.
- **Related ADR(s):** None yet / TBD if identity or domain architecture decision is required.
- **Related risk(s):** `RISK-003`, `RISK-009`, `RISK-010`, `RISK-012`, `RISK-017`.
- **Implementation task(s):** Phase 02 tasks for AD DS/DNS, forest/domain, identities, groups, policies, and authentication validation; Phase 03 replication/failover tasks; Phase 04 domain-client authentication tasks; later cloud identity, security, and lifecycle automation tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — tests to be defined during Phases 02–04, 11, 14, and 16.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; identity administration, authentication troubleshooting, and lifecycle runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Permanent domain/UPN design, final identity architecture, RBAC, privileged identities, tests, runbooks, and evidence remain open.

### REQ-002

- **Requirement ID:** `REQ-002`
- **Requirement summary:** The environment must use redundant Active Directory domain controllers
- **Business rationale / business need:** Identity and DNS are preliminary Critical services. DC01 must not remain the sole authentication/DNS dependency, and planned failover and recovery must demonstrate continuity through DC02.
- **Source document:** `docs/requirements.md` (authoritative); supported by `AGENTS.md`, `docs/project-charter.md` §§8–9 and 18, and `docs/business-profile.md` §§18 and 30.
- **Related project phase(s):** Phase 02 — Windows Server / DC01; Phase 03 — DC02 & Active Directory Replication; Phase 04 — DHCP, Group Policy & Windows Clients; Phase 15 — Backup & Disaster Recovery.
- **Related architecture diagram(s):** `architecture/diagrams/03-identity/01-ad-replication.puml`; `architecture/diagrams/05-cloud/01-hybrid-cloud.puml`; `architecture/diagrams/10-backup-dr/01-backup-dr.puml`.
- **Related ADR(s):** None yet / TBD if domain, sites, replication, or recovery architecture requires a decision.
- **Related risk(s):** `RISK-002`, `RISK-003`, `RISK-012`, `RISK-013`, `RISK-021`, `RISK-022`.
- **Implementation task(s):** Phase 02 DC01 tasks; all Phase 03 DC02, replication, DNS, FSMO, outage, recovery, and troubleshooting tasks; Phase 04 Milestone 1 tasks; relevant Phase 15 DC recovery tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — AD/DNS health, replication, DC01 outage, DC02 authentication/DNS failover, DC01 recovery, and restore tests to be defined during Phases 02–04 and 15.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; AD health, replication troubleshooting, failover, FSMO, and DC recovery runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Two-controller diagrams exist, but neither controller, replication, failure test, recovery test, or evidence exists.

### REQ-003

- **Requirement ID:** `REQ-003`
- **Requirement summary:** Remote employees must securely access corporate resources
- **Business rationale / business need:** Five named remote NRS employees need logged, role-appropriate access from managed corporate laptops while unauthorized access is denied and account revocation remains effective.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§2, 7, and 9 and `docs/business-profile.md` §§8, 15, 18, and 30.
- **Related project phase(s):** Phase 01 — Virtualization & Network Design; Phase 11 — Microsoft Cloud Identity; Phase 12 — Intune / MDM / Endpoint Management; Phase 13 — Remote Workforce; Phase 14 — Security Operations; Phase 19 — Citrix / Application Delivery. Phase 19 remains optional.
- **Related architecture diagram(s):** `architecture/diagrams/01-overview/01-enterprise-overview.puml`; `architecture/diagrams/02-network/01-network-topology.puml`; `architecture/diagrams/04-endpoints/01-mdm-intune.puml`; `architecture/diagrams/05-cloud/01-hybrid-cloud.puml`; `architecture/diagrams/06-security/01-security-controls.puml`.
- **Related ADR(s):** None yet / TBD for firewall, remote-access, identity, and endpoint architecture decisions.
- **Related risk(s):** `RISK-005`, `RISK-008`, `RISK-009`, `RISK-010`, `RISK-011`.
- **Implementation task(s):** Phase 01 remote/VPN network design and security tests; Phase 11 cloud identity tasks; Phase 12 managed-device/compliance tasks; all Phase 13 remote-workforce tasks; relevant Phase 14 access/security tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — connectivity, DNS, allowed/denied access, account disablement, MFA/compliance where supported, and logging tests to be defined during relevant phases.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; remote-access operations, access revocation, and troubleshooting runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** VPN/firewall platform, network design, identity integration, endpoint enforcement, licensing, tests, and evidence remain unresolved.

### REQ-004

- **Requirement ID:** `REQ-004`
- **Requirement summary:** IT must monitor server and application health
- **Business rationale / business need:** NRS IT needs timely visibility into Critical and High-priority infrastructure and applications so failures can be detected, investigated, communicated, and connected to operational workflows.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7–9 and `docs/business-profile.md` §§18, 25, and 30.
- **Related project phase(s):** Phase 07 — Observability; Phase 08 — ServiceNow IT Operations; Phase 14 — Security Operations; Phase 15 — Backup & Disaster Recovery; Phase 20 — Kubernetes.
- **Related architecture diagram(s):** `architecture/diagrams/01-overview/01-enterprise-overview.puml`; `architecture/diagrams/08-observability/01-prometheus-grafana.puml`.
- **Related ADR(s):** None yet / TBD if monitoring, logging, alerting, or notification architecture requires a decision.
- **Related risk(s):** `RISK-001`, `RISK-015`, `RISK-017`, `RISK-021`.
- **Implementation task(s):** All Phase 07 monitoring, logging, dashboard, alert, failure-path, and evidence tasks; Phase 08 alert-to-incident integration task; relevant monitoring recovery and Kubernetes observability tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — monitoring coverage and `Failure → Prometheus → Alert Rule → Alertmanager → Notification` tests to be defined during Phase 07 and later integrations.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; monitoring operations, alert response, tuning, and recovery runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Monitoring architecture, ownership, thresholds, notifications, retention, service coverage, tests, and evidence remain open.

### REQ-005

- **Requirement ID:** `REQ-005`
- **Requirement summary:** Lost or non-compliant managed devices must be remotely controlled
- **Business rationale / business need:** Managed endpoints—especially the five remote corporate laptops—need a controlled response when lost or non-compliant so access and synthetic business information can be protected.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7–9 and `docs/business-profile.md` §§14–15, 20, 27, and 30.
- **Related project phase(s):** Phase 08 — ServiceNow IT Operations; Phase 11 — Microsoft Cloud Identity; Phase 12 — Intune / MDM / Endpoint Management; Phase 13 — Remote Workforce; Phase 14 — Security Operations; Phase 16 — Automation.
- **Related architecture diagram(s):** `architecture/diagrams/04-endpoints/01-mdm-intune.puml`; `architecture/diagrams/06-security/01-security-controls.puml`; `architecture/diagrams/07-itsm/01-servicenow-flow.puml`.
- **Related ADR(s):** None yet / TBD if endpoint-management, compliance, or Conditional Access architecture requires a decision.
- **Related risk(s):** `RISK-004`, `RISK-005`, `RISK-009`, `RISK-010`, `RISK-015`.
- **Implementation task(s):** Phase 08 incident/asset workflow tasks; all applicable Phase 12 enrollment, compliance, lost-device, and non-compliant-device tasks; relevant Phase 13–14 access controls and Phase 16 workflow automation tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — lost-device lock/wipe and asset update plus non-compliance/access-blocking tests to be defined where licensing and lab capabilities permit.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; lost-device, non-compliance, access revocation, and endpoint response runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Microsoft eligibility/licensing, endpoint inventory, enrollment, compliance, Conditional Access, remote action capabilities, workflows, tests, and evidence are absent.

### REQ-006

- **Requirement ID:** `REQ-006`
- **Requirement summary:** IT must track hardware and software assets
- **Business rationale / business need:** Centralized IT needs lifecycle visibility for corporate endpoints, servers, network equipment, applications, and software/licenses, including the five required remote laptops.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7, 9, and 10 and `docs/business-profile.md` §§14, 24, and 30.
- **Related project phase(s):** Phase 08 — ServiceNow IT Operations; Phase 12 — Intune / MDM / Endpoint Management; Phase 16 — Automation.
- **Related architecture diagram(s):** None yet — existing ServiceNow diagram represents ITSM flow but does not depict ITAM or asset lifecycle.
- **Related ADR(s):** None yet / TBD if ITAM/CMDB platform or data architecture requires a decision.
- **Related risk(s):** `RISK-004`, `RISK-014`, `RISK-017`, `RISK-018`.
- **Implementation task(s):** Phase 08 ITAM and CMDB baseline tasks; applicable Phase 12 managed-device tasks; later approved asset workflow automation tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — asset creation, assignment, lifecycle, software/license, reconciliation, and relationship tests to be defined during Phase 08 and later integrations.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; asset intake, assignment, return, loss, reconciliation, retirement, and license-management procedures are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Final asset inventory, lifecycle states, ownership, data fields, ITAM/CMDB roles, reconciliation, tests, and evidence do not exist.

### REQ-007

- **Requirement ID:** `REQ-007`
- **Requirement summary:** IT must manage incidents, problems, changes, and requests
- **Business rationale / business need:** Employees need a consistent way to report issues and request services, while NRS IT needs controlled ownership, investigation, problem analysis, change, approval, knowledge, and closure workflows.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7, 9, and 10 and `docs/business-profile.md` §§13, 23, and 30.
- **Related project phase(s):** Phase 08 — ServiceNow IT Operations; Phase 16 — Automation.
- **Related architecture diagram(s):** `architecture/diagrams/07-itsm/01-servicenow-flow.puml`; `architecture/diagrams/09-applications/01-business-applications.puml`.
- **Related ADR(s):** None yet / TBD if ITSM platform or integration architecture requires a decision.
- **Related risk(s):** `RISK-004`, `RISK-015`, `RISK-017`, `RISK-018`.
- **Implementation task(s):** Phase 08 PDI, incident, problem, change, request, catalog, knowledge, CMDB, workflow-test, and evidence tasks; related Phase 16 API/automation tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — end-to-end incident, problem, change, request, approval, escalation, and knowledge tests to be defined during Phase 08 and later automation.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; ITSM administration, triage, escalation, change, request, and knowledge procedures are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Developer-instance eligibility, workflow design, roles, priorities, approvals, integrations, tests, and evidence remain open.

### REQ-008

- **Requirement ID:** `REQ-008`
- **Requirement summary:** Critical systems must be backed up and tested for recovery
- **Business rationale / business need:** NRS depends on identity, DNS, network/firewall, CRM, finance information, file services, monitoring, and configuration that must be recoverable after failure or loss.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7–9 and 23 and `docs/business-profile.md` §§18, 26, and 30.
- **Related project phase(s):** Phase 03 — DC02 & Active Directory Replication; Phase 07 — Observability; Phase 09 — CRM; Phase 15 — Backup & Disaster Recovery.
- **Related architecture diagram(s):** `architecture/diagrams/10-backup-dr/01-backup-dr.puml`; `architecture/diagrams/03-identity/01-ad-replication.puml`.
- **Related ADR(s):** None yet / TBD for backup, retention, recovery, and storage architecture decisions.
- **Related risk(s):** `RISK-002`, `RISK-012`, `RISK-013`, `RISK-021`, `RISK-022`.
- **Implementation task(s):** All Phase 15 definition, backup, restore-test, DR/runbook, and evidence tasks; supporting DC, monitoring, and CRM recovery-related tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — deleted-file, CRM/database, failed-VM, DC, configuration, and monitoring-system recovery tests to be defined during Phase 15.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; backup operations, restore procedures, and disaster-recovery runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Backup architecture, protected systems, RPO, RTO, retention, locations, recovery priority, implementations, tests, and evidence remain open.

### REQ-009

- **Requirement ID:** `REQ-009`
- **Requirement summary:** New employee onboarding should be automated where practical
- **Business rationale / business need:** NRS needs consistent, approved, role-appropriate identity, access, application, and asset provisioning with less avoidable manual effort and omission risk.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§7 and 9 and `docs/business-profile.md` §§21 and 30.
- **Related project phase(s):** Phase 08 — ServiceNow IT Operations; Phase 11 — Microsoft Cloud Identity; Phase 12 — Intune / MDM / Endpoint Management; Phase 16 — Automation.
- **Related architecture diagram(s):** None yet — current diagrams do not represent the complete onboarding workflow.
- **Related ADR(s):** None yet / TBD if identity lifecycle or automation architecture requires a decision.
- **Related risk(s):** `RISK-004`, `RISK-005`, `RISK-010`, `RISK-016`, `RISK-017`, `RISK-019`.
- **Implementation task(s):** Phase 08 request/catalog workflow tasks; Phase 11–12 identity/endpoint tasks; Phase 16 manual-workflow, PowerShell/Python/API, onboarding, and evidence tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — approved onboarding workflow, access, negative-access, error handling, rollback, and repeatability tests to be defined after the manual process is understood.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** Business-level workflow exists in `docs/business-profile.md` §21; detailed onboarding runbook is TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Sponsor/approvers, final access matrix, identity/application/asset integrations, manual runbook, automation design, tests, and evidence remain open.

### REQ-010

- **Requirement ID:** `REQ-010`
- **Requirement summary:** Infrastructure changes must be documented and testable
- **Business rationale / business need:** NRS needs reproducible, reviewable, secure changes with known scope, validation, rollback, evidence, and current documentation so the lab can be operated and represented truthfully.
- **Source document:** `docs/requirements.md` (authoritative); supported by `AGENTS.md`, `docs/master-build-roadmap.md`, `docs/project-charter.md` §§19–23, and `docs/business-profile.md` §§20, 23, and 30.
- **Related project phase(s):** Phase 00 — Project Governance; all implementation phases.
- **Related architecture diagram(s):** None specific — each affected PlantUML file must be updated when a change alters represented architecture.
- **Related ADR(s):** `architecture/decisions/ADR-000-template.md` is a template, not an ADR; no actual ADR exists yet.
- **Related risk(s):** `RISK-009`, `RISK-014`, `RISK-016`, `RISK-017`, `RISK-018`, `RISK-019`, `RISK-021`, `RISK-022`.
- **Implementation task(s):** Phase 00 governance, ADR, testing/evidence/runbook/change/incident standards, traceability, and completion-workflow tasks; documentation/test/evidence tasks in every implementation phase in `docs/tasks.md`.
- **Test ID(s):** TBD — governance/documentation conformance checks and phase-specific change validation tests have not been defined.
- **Evidence reference(s):** Current governed documents demonstrate planning activity, but formal requirement-validation evidence is not yet captured.
- **Runbook / operational documentation:** `changes/README.md`, `testing/README.md`, `evidence/README.md`, `runbooks/README.md`, and `incidents/README.md` define starter purposes only; detailed procedures/templates are TBD.
- **Current implementation status:** In Progress
- **Validation status:** Not Validated
- **Notes / gaps:** Git history is now available; detailed change/test/evidence procedures, traceability upkeep during implementation, implementation records, and requirement-validation evidence remain incomplete.

### REQ-011

- **Requirement ID:** `REQ-011`
- **Requirement summary:** Architecture must be documented in PlantUML
- **Business rationale / business need:** Current diagrams are needed to communicate intended systems, boundaries, dependencies, redundancy, security, operations, and recovery and to prevent undocumented design drift.
- **Source document:** `docs/requirements.md` (authoritative); supported by `AGENTS.md`, `docs/project-context.md`, `docs/master-build-roadmap.md`, and `docs/project-charter.md` §§8–10 and 19.
- **Related project phase(s):** Phase 00 — Project Governance; every phase that introduces or changes architecture.
- **Related architecture diagram(s):** All existing `.puml` files under `architecture/diagrams/`: overview, network, identity, endpoints, cloud, security, ITSM, observability, applications, and backup/DR.
- **Related ADR(s):** No actual ADR exists yet; `architecture/decisions/ADR-000-template.md` establishes future documentation impact requirements only.
- **Related risk(s):** `RISK-014`, `RISK-016`, `RISK-017`, `RISK-019`, `RISK-021`.
- **Implementation task(s):** Completed Phase 00 tasks “Create initial `architecture/diagrams/` structure” and “Establish PlantUML as the diagramming standard”; ongoing per-phase architecture/evidence tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — PlantUML syntax/rendering and architecture-to-implementation review tests have not been defined.
- **Evidence reference(s):** Existing `.puml` sources are present, but formal validation evidence is not yet captured.
- **Runbook / operational documentation:** `architecture/README.md` and `architecture/diagrams/README.md`; no diagram maintenance/runbook procedure beyond current guidance.
- **Current implementation status:** In Progress
- **Validation status:** Not Validated
- **Notes / gaps:** Diagrams are conceptual and may contain proposals; rendering evidence, accepted ADR linkage, and implemented-current-state verification are absent. Git-backed history is now available.

### REQ-012

- **Requirement ID:** `REQ-012`
- **Requirement summary:** Cloud resources should be provisioned with IaC where practical
- **Business rationale / business need:** Approved cloud infrastructure should be reproducible, reviewable, cost-controlled, testable, and less prone to undocumented manual drift.
- **Source document:** `docs/requirements.md` (authoritative); supported by `docs/project-charter.md` §§8–9 and 19 and `docs/business-profile.md` §30.
- **Related project phase(s):** Phase 17 — Azure & Infrastructure as Code; Phase 18 — GitHub Actions / CI/CD.
- **Related architecture diagram(s):** `architecture/diagrams/05-cloud/01-hybrid-cloud.puml` represents planned cloud context but does not depict IaC implementation.
- **Related ADR(s):** None yet / TBD if cloud or IaC architecture/tooling decisions require an ADR.
- **Related risk(s):** `RISK-004`, `RISK-007`, `RISK-009`, `RISK-014`, `RISK-017`, `RISK-019`, `RISK-021`.
- **Implementation task(s):** Phase 17 cost-control, tooling selection, IaC provisioning, plan/deployment/repeatability, cleanup, and evidence tasks; applicable Phase 18 validation/plan and CI tasks in `docs/tasks.md`.
- **Test ID(s):** TBD — formatting/validation, plan review, deployment, repeatability, security, cost-control, and cleanup tests to be defined during Phases 17–18.
- **Evidence reference(s):** Not yet captured.
- **Runbook / operational documentation:** None yet; IaC execution, approval, state, rollback, cost review, and cleanup runbooks are TBD.
- **Current implementation status:** Not Started
- **Validation status:** Not Validated
- **Notes / gaps:** Cloud eligibility, approved account/subscription, cost controls, tooling, state design, architecture decision, implementation, CI, tests, and evidence remain open.

## Major Traceability Gaps at Baseline

- No infrastructure requirement has been implemented.
- No actual ADR exists; `ADR-000` is a template only.
- No formal test IDs or test records exist.
- No requirement-validation evidence has been captured.
- No detailed operational runbook exists; only directory-purpose README files and business-level process expectations are present.
- The architecture library is conceptual and has not been validated against implemented state.
- Git-backed history is available beginning with the authorized Phase 00 baseline commit.
- Product, network, identity, remote-access, cloud, endpoint, monitoring, backup, and recovery decisions remain open in their designated phases.

## RTM Maintenance Process

Update this RTM when:

- a requirement is added, changed, clarified, reprioritized, blocked, or retired through the approved governance process;
- an ADR is Proposed, Accepted, Rejected, Deprecated, or Superseded when that status materially affects traceability;
- architecture changes or a diagram is created, updated, or retired;
- an implementation task starts, completes, becomes blocked, or changes scope;
- a test is created, executed, failed, remediated, or rerun;
- evidence is captured, replaced, invalidated, or archived;
- a runbook or other operational document is created or updated;
- a requirement receives partial or full validation, or validation fails; or
- a related risk materially changes rating, status, mitigation, contingency, or applicability.

For each update:

1. Keep requirement IDs stable and use the exact approved requirement wording.
2. Verify referenced phase names and order against `docs/master-build-roadmap.md`.
3. Verify referenced files and IDs exist; use `TBD`, `None yet`, or `Not yet captured` instead of inventing artifacts.
4. Link only meaningful risks and architecture relationships.
5. Keep implementation and validation statuses separate.
6. Do not mark a requirement Validated until traceable implementation, applicable testing, and evidence demonstrate satisfaction.
7. Record material changes in the appropriate governance/change history when that process is available.

## Review and Approval

The RTM is ready for project-owner review when all approved requirements appear exactly once, wording and phases match their authoritative sources, referenced files and IDs validate, and gaps are stated accurately. Project-owner approval establishes the current traceability baseline but does not validate any requirement.
