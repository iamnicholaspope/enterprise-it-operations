# Implementation Plan

> `docs/master-build-roadmap.md` is authoritative for phase numbering, names, order, dependencies, milestone sequencing, and completion criteria. This plan is a concise implementation summary.

## Phase 00 — Project Governance

- Establish project controls, governing documents, task and traceability registers, ADRs, testing, evidence, runbooks, and PlantUML structure.
- Establish Git and project-management workflows when explicitly authorized.

## Phase 01 — Virtualization & Network Design

- Design and implement the hypervisor, virtual networking, firewall/router, addressing, VLANs, routing, NAT, segmentation, and remote/VPN network.
- Validate permitted and prohibited traffic, Internet access, management restrictions, and firewall logging.

## Phase 02 — Windows Server / DC01

- Deploy Windows Server 2025 Evaluation as `DC01` with AD DS, DNS, the forest/domain, OUs, users, groups, administrative controls, password policy, and initial Group Policies.
- Validate AD health, DNS, authentication, membership, and policy processing.

## Phase 03 — DC02 & Active Directory Replication

- Deploy `DC02` with AD DS, DNS, replication, Global Catalog where appropriate, Sites and Services, and FSMO role awareness.
- Test DC01 failure, DC02 authentication/DNS continuity, DC01 recovery, and resumed replication.

## Phase 04 — DHCP, Group Policy & Windows Clients

- Configure DHCP, managed Windows clients, domain joining, and department/security Group Policies.
- Complete Milestone 1 by validating DHCP, DNS, GPOs, client behavior, and authentication/DNS failover during a planned DC01 outage and recovery.

## Phase 05 — Linux Foundation

- Deploy `LINUX01` and establish Linux administration, SSH, identity, permissions, services, packages, networking, logging, scheduling, Nginx, firewalling, and TLS concepts.

## Phase 06 — Docker & Docker Compose

- Establish Docker and Compose fundamentals, networks, persistent volumes, environment configuration, logging, and health checks without committing secrets.

## Phase 07 — Observability

- Deploy Prometheus, Grafana, Alertmanager, Loki, Windows Exporter, and Node Exporter.
- Monitor core infrastructure and validate the failure-to-notification path.

## Phase 08 — ServiceNow IT Operations

- Establish a ServiceNow developer environment where available and configure ITSM, ITAM, CMDB, knowledge, and service catalog capabilities.
- Prepare for later Alertmanager-to-ServiceNow incident integration.

## Phase 09 — CRM

- Implement SuiteCRM as the primary free option and configure the lead-to-sale workflow, access controls, reporting, dashboards, and appropriate integrations.

## Phase 10 — Email Protocol Lab

- Build an internal email protocol lab, potentially using Postfix and Dovecot, covering SMTP, IMAP, POP3, TLS, authentication, DNS, MX, routing, and troubleshooting.

## Phase 11 — Microsoft Cloud Identity

- Configure eligible Microsoft 365 and Entra ID developer/trial resources and learn cloud/hybrid identity, SSO, MFA, RBAC, lifecycle, and administration.

## Phase 12 — Intune / MDM / Endpoint Management

- Where licensing permits, configure device enrollment, MDM/MAM, BYOD, compliance, application deployment, and endpoint security.
- Validate lost-device and non-compliant-device scenarios.

## Phase 13 — Remote Workforce

- Securely support five remote employees using an appropriate VPN, identity controls, endpoint compliance, and firewall policies.
- Validate permitted connectivity, denied access, account disablement, DNS, and logging.

## Phase 14 — Security Operations

- Apply and exercise layered controls for privilege, RBAC, MFA, Conditional Access, segmentation, Defender, compliance, TLS, certificates, accounts, auditing, and events.
- Consider Wazuh only as an optional justified addition.

## Phase 15 — Backup & Disaster Recovery

- Define RPO, RTO, retention, frequency, locations, and recovery priorities.
- Implement appropriate free/community backup methods and validate required file, application, VM, DC, configuration, and monitoring recoveries.

## Phase 16 — Automation

- Automate only documented and understood manual workflows using PowerShell, Python, and approved APIs.
- Progress toward the ServiceNow-to-identity/application onboarding workflow.

## Phase 17 — Azure & Infrastructure as Code

- Establish Azure cost controls before deployment.
- Use Terraform and/or OpenTofu for practical, repeatable cloud resources and hybrid-network concepts.

## Phase 18 — GitHub Actions / CI/CD

- Add automated validation or deployment only where it improves existing workflows, including code, IaC, documentation, PlantUML, containers, and security checks.

## Phase 19 — Citrix / Application Delivery

- Optionally explore Citrix or XenServer application delivery and VDI concepts when licensing/evaluation resources permit.

## Phase 20 — Kubernetes

- Begin only after Linux, Docker, Compose, container networking/storage, TLS, observability, and troubleshooting prerequisites are established.
- Integrate Kubernetes workloads with Prometheus and Grafana, with later OpenTelemetry, Loki, and Tempo extensions.

## Dependency and Milestone Rules

- Follow the phase order above unless the master roadmap explicitly permits otherwise.
- Do not rush into cloud, ServiceNow, CRM, or Kubernetes before their prerequisites.
- Milestone 1 spans Phases 01–04 and succeeds only when identity and DNS remain functional during a planned DC01 outage and recovery is documented.
- Apply the master roadmap's per-phase documentation requirements and Definition of Done before marking tasks complete.
