# Project Risk Register

> **Baseline approval:** The project owner approved this document as the current Phase 00 risk baseline on 2026-08-28. Its task remains `[~]` until all applicable Definition of Done evidence, including Git-backed change history, is available.

## Purpose and Scope

This register records risks that could affect the successful implementation, validation, operation, or evidentiary value of the Enterprise IT Operations Lab for Northstar Ridge Solutions, LLC (NRS). It applies across Phases 00–20 and should be reviewed as the project, architecture, licensing, exposure, and operating procedures evolve.

All company information and operational records in this project are synthetic lab data. Risk descriptions model realistic concerns but do not assert that an incident, loss, outage, or control failure has occurred.

## Rating Method

Likelihood and impact are qualitative planning judgments, not numerical probabilities or financial estimates.

- **Likelihood — Low:** Not expected under normal lab conditions, but plausible.
- **Likelihood — Medium:** Credible during the project and should be actively managed.
- **Likelihood — High:** Expected to arise or recur without sustained controls.
- **Impact — Low:** Limited effect that does not materially prevent a phase objective.
- **Impact — Medium:** Meaningful rework, delay, loss of capability, or reduced evidence quality.
- **Impact — High:** Could prevent a mandatory requirement, milestone, secure operation, or recovery objective from being demonstrated.

Overall ratings use this matrix:

| Likelihood \ Impact | Low | Medium | High |
|---|---|---|---|
| Low | Low | Low | Medium |
| Medium | Low | Medium | High |
| High | Medium | High | Critical |

A rating may be adjusted only when the rationale is documented. No specific probability, outage duration, dollar loss, RPO, RTO, or SLA is implied.

## Status Definitions

- **Open:** Treatment is planned or underway and residual exposure remains.
- **Monitoring:** Current controls are considered adequate for now, but conditions may change.
- **Accepted:** The project owner has explicitly accepted the residual risk.
- **Mitigated:** Planned controls are implemented and validated; continued monitoring may still be required.
- **Realized:** The risk occurred and must be linked to an incident or issue record.
- **Closed:** The risk no longer applies or has been fully retired with supporting rationale.

## Risk Summary

| Risk ID | Category | Short description | Likelihood | Impact | Overall | Owner role | Status |
|---|---|---|---|---|---|---|---|
| RISK-001 | Capacity | Physical host resources are insufficient | Medium | Medium | Medium | IT Manager | Open |
| RISK-002 | Availability | Single virtualization host fails | Medium | High | High | Systems Administrator | Open |
| RISK-003 | Licensing | Windows Server evaluation expires | Medium | High | High | IT Manager | Open |
| RISK-004 | External service | Developer/trial services expire or change | High | Medium | High | IT Manager | Open |
| RISK-005 | Licensing | Microsoft cloud capabilities are unavailable | Medium | Medium | Medium | IT Manager | Open |
| RISK-006 | Licensing | Citrix evaluation resources are unavailable | High | Low | Medium | Project Owner | Monitoring |
| RISK-007 | Cost | Azure or cloud usage creates unexpected charges | Medium | High | High | Project Owner | Open |
| RISK-008 | Security | Lab services are accidentally exposed publicly | Medium | High | High | Security/Risk Reviewer | Open |
| RISK-009 | Security | Credentials or secrets are disclosed | Medium | High | High | IT Manager | Open |
| RISK-010 | Access control | Excess privilege or weak RBAC enables misuse | Medium | High | High | IT Manager | Open |
| RISK-011 | Network security | Firewall or segmentation is misconfigured | Medium | High | High | Systems Administrator | Open |
| RISK-012 | Identity availability | Active Directory or DNS fails | Medium | High | High | Systems Administrator | Open |
| RISK-013 | Recoverability | Backups fail or restores remain untested | Medium | High | High | Systems Administrator | Open |
| RISK-014 | Configuration | Configuration drift reduces repeatability | Medium | Medium | Medium | Systems Administrator | Open |
| RISK-015 | Observability | Monitoring or alerting is ineffective | Medium | High | High | IT Manager | Open |
| RISK-016 | People | Project depends on one administrator/operator | High | Medium | High | Project Owner | Open |
| RISK-017 | Documentation | Documentation becomes stale | High | Medium | High | IT Manager | Open |
| RISK-018 | Governance | Scope creep dilutes business value | High | Medium | High | Project Owner | Open |
| RISK-019 | Sequencing | Technology is implemented before prerequisites | Medium | Medium | Medium | IT Manager | Open |
| RISK-020 | Data integrity | Synthetic data is mistaken for real data | Low | Medium | Low | Project Owner | Monitoring |
| RISK-021 | Evidence | Lab configuration or evidence is lost | Medium | High | High | Systems Administrator | Open |
| RISK-022 | Test safety | Intentionally broken scenarios leave vulnerabilities | Medium | High | High | Security/Risk Reviewer | Open |

## Detailed Risks

### RISK-001 — Limited Physical Host Resources

- **Category:** Capacity
- **Description:** Available CPU, memory, storage, or network capacity may be insufficient to run the planned systems concurrently or produce representative results.
- **Cause:** The lab is expected to use limited, low-cost physical resources while the roadmap adds many virtualized services.
- **Potential impact:** Phases may be delayed, systems may need to be stopped between tests, performance evidence may be misleading, or planned integrations may need reduced scale.
- **Likelihood:** Medium
- **Impact severity:** Medium
- **Overall rating:** Medium
- **Mitigation:** Inventory host capacity before Phase 01; right-size VMs; document minimum and actual resources; phase workloads; monitor utilization; avoid adding technology without business justification.
- **Contingency / response:** Reduce concurrency or lab scale, move eligible noncritical workloads to another approved resource, or document the limitation and defer affected tests.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-004`, `REQ-010`
- **Related phase(s):** Phase 01 and all infrastructure phases

### RISK-002 — Single Virtualization Host Failure

- **Category:** Availability
- **Description:** A failure of the only virtualization host could make most or all lab services unavailable and could damage local configurations or evidence.
- **Cause:** The project may operate on one physical host even though guest services later demonstrate redundancy.
- **Potential impact:** Broad lab outage, delayed testing, loss of state, inability to demonstrate service recovery, or confusion between guest-level redundancy and host-level resilience.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Document the host as a single point of failure; protect VM configurations and critical evidence; use recoverable exports/backups; test recovery procedures; avoid claiming host-level high availability.
- **Contingency / response:** Repair or replace the host, restore approved VM/configuration backups, rebuild from documented configuration, and record the event and recovery evidence.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-008`, `REQ-010`
- **Related phase(s):** Phases 01, 15, and all hosted phases

### RISK-003 — Windows Server Evaluation Expiration

- **Category:** Licensing
- **Description:** Windows Server 2025 Evaluation may expire before identity, replication, client, security, backup, or recovery work is complete.
- **Cause:** Evaluation licensing is time-limited and the roadmap spans many phases.
- **Potential impact:** Service interruption, forced rebuild or migration, inability to repeat tests, or inaccurate licensing claims.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Record installation and expiration information; schedule core Windows phases and evidence while evaluation rights are valid; maintain rebuild and recovery documentation; distinguish evaluation from production licensing.
- **Contingency / response:** Use an approved renewed evaluation or properly licensed alternative where permitted, rebuild from documented state, or record the resulting scope limitation.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-001`, `REQ-002`, `REQ-010`
- **Related phase(s):** Phases 02–04, 11–16

### RISK-004 — Developer or Trial Service Expiration, Loss, or Change

- **Category:** External service
- **Description:** Vendor developer environments, trials, evaluation programs, or features may expire, be revoked, change terms, or be discontinued.
- **Cause:** The project relies where practical on external programs that NRS does not control.
- **Potential impact:** Planned integrations or retesting may become unavailable, evidence may become difficult to reproduce, or scope may need adjustment.
- **Likelihood:** High
- **Impact severity:** Medium
- **Overall rating:** High
- **Mitigation:** Record license class, eligibility, constraints, and relevant dates; avoid designing mandatory outcomes around unconfirmed access; preserve sanitized documentation and exports; identify acceptable conceptual or alternative coverage.
- **Contingency / response:** Use an approved alternative, document the unavailable capability accurately, revise optional scope through change control, and do not claim hands-on validation that did not occur.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-005`, `REQ-007`, `REQ-010`
- **Related phase(s):** Phases 08, 11, 12, 17, 19

### RISK-005 — Microsoft Cloud Licensing or Trial Unavailability

- **Category:** Licensing
- **Description:** Suitable Microsoft 365, Entra ID, Intune, Conditional Access, Defender, or related developer/trial capabilities may not be available.
- **Cause:** Eligibility, tenant availability, feature licensing, or trial terms may not support the planned lab scenarios.
- **Potential impact:** Cloud identity, compliance, lost-device, access-control, or endpoint scenarios may be limited to design evidence rather than full implementation.
- **Likelihood:** Medium
- **Impact severity:** Medium
- **Overall rating:** Medium
- **Mitigation:** Confirm eligibility before design commitments; map mandatory requirements to available capabilities; clearly label conceptual, partial, and validated work; avoid paid licensing without approval.
- **Contingency / response:** Use available vendor learning resources or approved alternatives, narrow the affected scenario, and formally document limitations without representing them as completed implementation.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-001`, `REQ-003`, `REQ-005`, `REQ-009`
- **Related phase(s):** Phases 11–14, 16

### RISK-006 — Citrix Licensing or Evaluation Unavailability

- **Category:** Licensing
- **Description:** Citrix or XenServer learning and evaluation resources may be unavailable or unsuitable.
- **Cause:** Phase 19 is optional and dependent on external licensing/evaluation access and demonstrated business value.
- **Potential impact:** The optional application-delivery phase may be reduced, deferred, or omitted; mandatory project requirements need not fail solely for this reason.
- **Likelihood:** High
- **Impact severity:** Low
- **Overall rating:** Medium
- **Mitigation:** Confirm business value and eligibility before planning implementation; keep Phase 19 explicitly conditional; avoid unsupported résumé claims.
- **Contingency / response:** Document the licensing constraint and omit or defer Phase 19 with project-owner approval.
- **Owner role:** Project Owner
- **Status:** Monitoring
- **Related requirement(s):** `REQ-003`, `REQ-010`
- **Related phase(s):** Phase 19

### RISK-007 — Unexpected Azure or Cloud Charges

- **Category:** Cost
- **Description:** Misconfigured, forgotten, or misunderstood cloud resources could generate unapproved charges.
- **Cause:** Consumption pricing, resource dependencies, persistent resources, or incomplete cleanup can exceed the project's free/low-cost constraint.
- **Potential impact:** Unplanned cost, forced termination of cloud work, or loss of project-owner confidence.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Require explicit approval before paid resources; establish budgets, alerts, cost review, tagging, IaC, and cleanup procedures before deployment; prefer free/developer options.
- **Contingency / response:** Stop or remove the exact approved resources using documented procedures, review charges, preserve necessary evidence, and record the event through change/incident processes as appropriate.
- **Owner role:** Project Owner
- **Status:** Open
- **Related requirement(s):** `REQ-010`, `REQ-012`
- **Related phase(s):** Phase 17

### RISK-008 — Accidental Public Exposure of Lab Services

- **Category:** Security
- **Description:** A lab service, management interface, domain controller, mail endpoint, or later Internet/domain integration could be exposed publicly without adequate review or controls.
- **Cause:** Firewall/NAT mistakes, temporary testing, cloud defaults, DNS changes, tunneling, or premature domain use.
- **Potential impact:** Unauthorized access, compromise, abuse of lab services, disclosure of credentials or configuration, and loss of trustworthy evidence.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Keep unfinished services private; prohibit direct DC and management-interface exposure; require documented security review, TLS, deliberate DNS, firewall rules, logging, and approval before public exposure; review future domain decisions through an ADR/change.
- **Contingency / response:** Remove exposure immediately, preserve relevant logs, rotate affected secrets, assess systems, create an incident record, remediate, and retest before any re-exposure.
- **Owner role:** Security/Risk Reviewer
- **Status:** Open
- **Related requirement(s):** `REQ-003`, `REQ-010`, `REQ-011`
- **Related phase(s):** Phases 01, 10, 13, 14, 17, 19, 20

### RISK-009 — Credential or Secret Exposure

- **Category:** Security
- **Description:** Passwords, tokens, API keys, private keys, or other secrets could enter Git, documentation, screenshots, logs, exports, images, or examples.
- **Cause:** Manual handling, unsanitized evidence, embedded configuration, environment files, or automation mistakes.
- **Potential impact:** Unauthorized access, compromised services, invalid evidence, and required secret rotation or rebuild.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Use secure secret storage and placeholders; sanitize artifacts; exclude secret files; scan applicable repositories and CI workflows; review screenshots/exports before retention; never use real production secrets.
- **Contingency / response:** Revoke and rotate exposed credentials, remove exposure from active systems, preserve a safe incident record, assess access, remediate history through an approved procedure when Git exists, and retest.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-010`, `REQ-012`
- **Related phase(s):** All phases

### RISK-010 — Excessive Privilege or Poor RBAC

- **Category:** Access control
- **Description:** Users or administrators may receive broader access than required, including through everyday accounts or direct user permissions.
- **Cause:** Incomplete role design, convenience assignments, inherited permissions, weak separation of duties, or lack of access review.
- **Potential impact:** Unauthorized changes, disclosure of restricted synthetic data, security-control bypass, or inability to demonstrate least privilege.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Design role/resource groups; apply least privilege; separate everyday and privileged identities where approved; document approvals; test effective access; review group membership and administrative roles.
- **Contingency / response:** Remove excess access, disable affected privileged paths, review activity, create an incident/change record where appropriate, correct group design, and retest authorization.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-001`, `REQ-003`, `REQ-005`, `REQ-010`
- **Related phase(s):** Phases 02–04, 08–14, 16–20

### RISK-011 — Firewall or Network Segmentation Misconfiguration

- **Category:** Network security
- **Description:** Routing, NAT, VLAN, or firewall rules may allow prohibited traffic or block required business traffic.
- **Cause:** Design errors, rule-order mistakes, overly broad rules, configuration drift, or inadequate negative testing.
- **Potential impact:** Unauthorized access between trust zones, remote-access failure, loss of service, or public exposure.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Approve network design before implementation; use least-access rules; document rule purpose; test both permitted and prohibited flows; restrict management access; enable logging; review changes.
- **Contingency / response:** Isolate affected networks, revert the exact change using an approved rollback, review logs, correct rules, and rerun connectivity and denial tests.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-003`, `REQ-010`, `REQ-011`
- **Related phase(s):** Phases 01, 13, 14, 17, 19, 20

### RISK-012 — Active Directory or DNS Failure

- **Category:** Identity availability
- **Description:** Failure or corruption of AD DS, DNS, replication, or both domain controllers could prevent authentication and dependent services.
- **Cause:** Misconfiguration, replication faults, incorrect DNS, host failure, unsafe changes, or incomplete recovery preparation.
- **Potential impact:** Loss of employee authentication, name resolution, policy processing, remote access, and dependent application functionality.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Deploy DC01 and DC02 as required; configure DNS redundancy and replication; monitor health; document FSMO roles; perform required failure, troubleshooting, backup, and recovery exercises.
- **Contingency / response:** Fail over to the healthy controller where possible, diagnose with approved tools, restore service using documented recovery steps, validate replication/DNS, and record evidence and incidents.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-001`, `REQ-002`, `REQ-008`
- **Related phase(s):** Phases 02–04, 07, 15

### RISK-013 — Backup Failure or Untested Restore

- **Category:** Recoverability
- **Description:** Backups may be incomplete, inaccessible, corrupted, misconfigured, or falsely assumed valid without successful restore testing.
- **Cause:** Missing coverage, failed jobs, inadequate monitoring, shared failure domains, undocumented credentials, or skipped recovery exercises.
- **Potential impact:** Permanent loss of lab configuration or synthetic business data, extended rebuild effort, and failure to satisfy recovery requirements.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Define coverage and recovery priorities; monitor backup results; maintain protected copies; document procedures; test the required file, database, VM, DC, configuration, and monitoring recoveries.
- **Contingency / response:** Use the best available valid copy or rebuild from documented configuration/IaC, record gaps, correct the backup design, and repeat restore testing.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-008`, `REQ-010`
- **Related phase(s):** Phases 15–18

### RISK-014 — Configuration Drift

- **Category:** Configuration
- **Description:** Actual systems may diverge from approved designs, documentation, scripts, or IaC.
- **Cause:** Undocumented manual changes, repeated troubleshooting, expired environments, rebuilds, or incomplete change control.
- **Potential impact:** Inconsistent behavior, unreliable tests, harder recovery, security gaps, and evidence that no longer represents current state.
- **Likelihood:** Medium
- **Impact severity:** Medium
- **Overall rating:** Medium
- **Mitigation:** Use change records, version-controlled configuration when authorized, repeatable scripts/IaC, baseline exports, periodic comparison, and documentation updates.
- **Contingency / response:** Identify the authoritative state, reconcile or revert drift through an approved change, validate service and security behavior, and refresh evidence.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-010`, `REQ-011`, `REQ-012`
- **Related phase(s):** All implementation phases

### RISK-015 — Insufficient Monitoring, Alert Fatigue, or Ineffective Alerts

- **Category:** Observability
- **Description:** Important failures may go undetected, while noisy or unactionable alerts may be ignored.
- **Cause:** Missing coverage, poor thresholds, absent notifications, inadequate context, excessive severity, or failure to test alert paths.
- **Potential impact:** Delayed diagnosis, unrecognized backup/security/service failures, ineffective incident workflows, or misleading monitoring evidence.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Monitor documented critical services; define actionable alerts and ownership; tune thresholds; test failure-to-notification paths; review false positives, missed events, and alert usefulness.
- **Contingency / response:** Use direct service checks and logs, correct coverage or routing, suppress or tune noisy alerts through change control, and repeat failure tests.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-004`, `REQ-007`, `REQ-008`, `REQ-010`
- **Related phase(s):** Phases 07, 08, 14, 15, 20

### RISK-016 — Dependency on One Administrator or Lab Operator

- **Category:** People
- **Description:** Project knowledge, access, and recovery ability may depend on one person.
- **Cause:** The lab may be built and operated primarily by a single individual despite modeling a three-person IT department.
- **Potential impact:** Work pauses when the operator is unavailable, mistakes receive limited review, and recovery or maintenance may rely on undocumented knowledge.
- **Likelihood:** High
- **Impact severity:** Medium
- **Overall rating:** High
- **Mitigation:** Maintain clear runbooks, diagrams, decisions, inventories, tests, and recovery steps; avoid personal-only credentials; use repeatable automation; request review at phase gates.
- **Contingency / response:** Reconstruct state from governed documentation and evidence, rotate inaccessible credentials through approved recovery, and document knowledge gaps.
- **Owner role:** Project Owner
- **Status:** Open
- **Related requirement(s):** `REQ-009`, `REQ-010`, `REQ-011`
- **Related phase(s):** Phase 00 and all implementation phases

### RISK-017 — Stale or Conflicting Documentation

- **Category:** Documentation
- **Description:** Plans, tasks, architecture, runbooks, requirements, evidence, and actual configuration may become inconsistent.
- **Cause:** Changes are made without updating all affected artifacts, or proposals are mistaken for approved implementation.
- **Potential impact:** Incorrect implementation, unsafe recovery, duplicated work, weak traceability, and unreliable portfolio claims.
- **Likelihood:** High
- **Impact severity:** Medium
- **Overall rating:** High
- **Mitigation:** Review governing documents before work; update affected documentation in the same change; label proposed versus approved state; validate cross-document references; use the master roadmap and tasks as defined authorities.
- **Contingency / response:** Pause dependent work, identify the authoritative source, reconcile documents, record the correction, and revalidate affected tests/evidence.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-010`, `REQ-011`
- **Related phase(s):** All phases

### RISK-018 — Scope Creep

- **Category:** Governance
- **Description:** Technologies or scenarios may be added for exposure rather than a documented business requirement.
- **Cause:** The roadmap covers many domains and optional tools can appear attractive before core outcomes are complete.
- **Potential impact:** Delayed milestones, incomplete core services, shallow evidence, higher resource use, and reduced business coherence.
- **Likelihood:** High
- **Impact severity:** Medium
- **Overall rating:** High
- **Mitigation:** Require requirement traceability, phase sequencing, explicit scope approval, cost/licensing review, and evidence criteria before adding work; keep optional phases conditional.
- **Contingency / response:** Defer or remove unsupported work through project-owner review and refocus on the current phase and mandatory requirements.
- **Owner role:** Project Owner
- **Status:** Open
- **Related requirement(s):** `REQ-010`
- **Related phase(s):** All phases

### RISK-019 — Implementation Before Prerequisites Are Understood

- **Category:** Sequencing
- **Description:** A technology may be deployed before its business workflow, architecture, dependencies, manual operation, security, or failure modes are understood.
- **Cause:** Skipping roadmap order or treating installation as completion.
- **Potential impact:** Rework, insecure defaults, brittle integration, failed tests, poor troubleshooting, and automation of an incorrect process.
- **Likelihood:** Medium
- **Impact severity:** Medium
- **Overall rating:** Medium
- **Mitigation:** Enforce the master roadmap dependency order; document requirements and architecture first; complete prerequisite learning and manual workflows; review readiness before future phases.
- **Contingency / response:** Stop the premature work, document current state, revert or isolate it safely, complete prerequisites, and resume only after approval.
- **Owner role:** IT Manager
- **Status:** Open
- **Related requirement(s):** `REQ-009`, `REQ-010`, `REQ-011`, `REQ-012`
- **Related phase(s):** All phases, especially Phases 06, 16, 17, 18, and 20

### RISK-020 — Synthetic Data Confused with Real Data

- **Category:** Data integrity
- **Description:** Synthetic employees, customers, assets, incidents, finance information, or scenarios may be mistaken for real business records or completed events.
- **Cause:** Artifacts lack a synthetic-data label or are reused outside their lab context.
- **Potential impact:** Misleading documentation, inappropriate portfolio claims, accidental mixing with real information, or incorrect operational conclusions.
- **Likelihood:** Low
- **Impact severity:** Medium
- **Overall rating:** Low
- **Mitigation:** Keep explicit synthetic-data notices; use reserved placeholders such as `example.invalid`; label scenarios and evidence accurately; avoid real personal, customer, financial, or regulated data.
- **Contingency / response:** Correct or withdraw the misleading artifact, separate any real data immediately, review related records, and document the correction.
- **Owner role:** Project Owner
- **Status:** Monitoring
- **Related requirement(s):** `REQ-010`
- **Related phase(s):** All phases

### RISK-021 — Loss of Lab Configuration or Evidence

- **Category:** Evidence
- **Description:** Configuration files, diagrams, scripts, test results, screenshots, logs, or other evidence may be lost or become unreadable.
- **Cause:** Host/storage failure, accidental deletion, corruption, incomplete backup, service expiration, or absent version history.
- **Potential impact:** Inability to reproduce work, validate requirements, recover systems, or support truthful portfolio claims.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Maintain organized evidence and configuration structures; use appropriate backups and exports; use version history when Git is authorized; sanitize artifacts; periodically verify readability and restore paths.
- **Contingency / response:** Restore from available copies, reconstruct from systems and documentation, record missing evidence honestly, and repeat tests where possible.
- **Owner role:** Systems Administrator
- **Status:** Open
- **Related requirement(s):** `REQ-008`, `REQ-010`, `REQ-011`
- **Related phase(s):** Phase 00 and all implementation phases

### RISK-022 — Intentionally Broken Test Scenario Leaves Residual Vulnerability

- **Category:** Test safety
- **Description:** Failure, troubleshooting, or security exercises may leave unsafe configuration, disabled protection, exposed services, or unresolved faults after testing.
- **Cause:** Deliberate misconfiguration is required for learning, but isolation, rollback, validation, or change records may be incomplete.
- **Potential impact:** Later tests run against an insecure or invalid baseline, services remain exposed, evidence becomes unreliable, or other systems are affected.
- **Likelihood:** Medium
- **Impact severity:** High
- **Overall rating:** High
- **Mitigation:** Define prerequisites, isolation, exact targets, safety limits, expected results, rollback, and post-test validation before destructive or security-sensitive exercises; use snapshots/backups where appropriate.
- **Contingency / response:** Isolate affected systems, restore the approved baseline, rotate exposed credentials where necessary, validate security and service health, and record a realized incident/issue.
- **Owner role:** Security/Risk Reviewer
- **Status:** Open
- **Related requirement(s):** `REQ-008`, `REQ-010`
- **Related phase(s):** Phases 01–04, 07, 12–15, 20

## Risk Management Process

### Adding a Risk

1. Confirm the condition is uncertain and could affect an objective; do not record every unresolved design choice as a risk.
2. Assign the next unused stable `RISK-###` identifier. Never reuse or renumber an existing ID.
3. Record every required field and link applicable requirements and phases.
4. Assign an owner role and initial status.
5. Apply the qualitative rating matrix and document any justified exception.

### Reviewing and Updating Risks

- Review the register at Phase 00 approval, before each phase begins, at phase completion, after material architecture/licensing/exposure changes, and after relevant incidents or failed tests.
- The owner role reviews controls, new evidence, external changes, and residual exposure.
- Update likelihood, impact, overall rating, mitigation, contingency, status, and links when conditions change.
- Preserve the stable ID and enough history in a change record or version history to explain material reassessment.

### Closing or Accepting Risks

- Mark a risk **Mitigated** only after planned controls are implemented and validated.
- Mark a risk **Accepted** only with explicit project-owner acceptance and documented rationale.
- Mark a risk **Closed** only when it no longer applies or treatment fully retires it; record closure rationale and supporting evidence.
- Do not delete closed risks or reuse their identifiers.

### Realized Risks and Links

- When a risk occurs, change its status to **Realized** and create or link an incident or issue record where appropriate.
- Link related ADRs, change records, incident records, tests, runbooks, configuration, and evidence when those artifacts exist.
- After response and recovery, reassess residual likelihood and impact; do not close the risk merely because the immediate incident ended.

## Assumptions Affecting This Register

- The lab may rely on one physical virtualization host; the final host design and capacity are not yet approved.
- A single primary lab operator may perform several role-based responsibilities even though NRS models a three-person IT department.
- Qualitative ratings describe planning priority and are not statistical forecasts.
- Optional capabilities may be deferred or omitted with project-owner approval when their absence does not prevent mandatory requirements.
- Git-backed version history will become available only after Git initialization is explicitly authorized.

## Unresolved Decisions Affecting Risk Treatment

- Physical host capacity, redundancy, storage, and backup location
- Final hypervisor, firewall, VPN, addressing, VLAN, routing, and exposure design
- Permanent AD domain, UPN suffix, public domain, and production email domain
- Available evaluation, developer, trial, and paid licensing and relevant expiration dates
- Approved cloud accounts, spending authority, budgets, alerts, and cleanup ownership
- Final RBAC, privileged-account, and access-review design
- Monitoring coverage, thresholds, notification ownership, and log retention
- Backup coverage, RPO, RTO, retention, frequency, location, and recovery priority
- Detailed incident, escalation, change, and approval workflows
- Whether optional Citrix/application-delivery work is justified and available

## Review and Approval

This register is ready for project-owner review when all required fields are populated, IDs and requirement references validate, rating calculations are consistent, and mitigations do not prematurely finalize open architecture decisions. Approval of the register accepts it as the current planning baseline; it does not accept residual risks unless a risk is individually marked **Accepted** with rationale.
