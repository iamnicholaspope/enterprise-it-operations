# Project Tasks

> Task status is the source of truth for implementation progress. Phase numbering, names, order, dependencies, milestones, and completion criteria come from `docs/master-build-roadmap.md`.

## Task Completion Standard

Before marking an implementation task `[x]`, apply the master roadmap's Definition of Done: document configuration and security considerations, record testing and failure testing where applicable, capture sanitized evidence, update PlantUML and runbooks when affected, update requirement traceability, and commit relevant Git changes when Git is available and authorized.

## Project-Management Convention

The GitHub Project is the visual workflow for GitHub Issues, which are executable work items. This file remains the repository-controlled task and governance register. `docs/master-build-roadmap.md` remains authoritative for phase order and dependencies, `docs/requirements.md` remains authoritative for requirements, and `docs/requirements-traceability-matrix.md` records requirement traceability. GitHub Project fields, views, and issue states must reflect these sources rather than replace or reinterpret them.

## Phase 00 — Project Governance

- [x] Create initial `architecture/diagrams/` structure
- [x] Establish PlantUML as the diagramming standard
- [x] Create AI project instruction structure
- [x] Initialize Git repository when explicitly authorized
- [x] Create project charter
- [x] Create detailed business profile
- [ ] Review and approve requirements register
- [ ] Maintain authoritative master build roadmap
- [x] Create risk register
- [x] Create ADR template
- [x] Create requirements traceability matrix
- [x] GitHub Repository Publication (`REQ-010`)
  - [x] Confirm repository publication safety
  - [x] Establish intended GitHub owner/account
  - [x] Authenticate GitHub tooling
  - [x] Create or connect the GitHub repository
  - [x] Configure `origin`
  - [x] Push `main`
  - [x] Verify local `HEAD` matches `origin/main`
  - [x] Verify repository visibility
  - [x] Verify the working tree remains clean
  - [x] Record repository URL and publication evidence
    - Evidence (2026-08-28): public repository `https://github.com/iamnicholaspope/enterprise-it-operations`; local `main` tracks `origin/main`; initial published baseline verified at commit `1b6677f2da6fa640f2a44076d3b0deeb8699f0da`.
- [ ] Establish testing, evidence, runbook, change, and incident standards
- [ ] Verify tasks can be traced to requirements
- [x] Create GitHub Project/Kanban board when explicitly authorized
  - Evidence (2026-08-28): public user project `Enterprise IT Operations Lab` (`https://github.com/users/iamnicholaspope/projects/1`) is linked to the repository; Status uses `BACKLOG`, `READY`, `IN PROGRESS`, `TESTING`, and `DONE`; Phase, Requirement, Priority, and Work Type fields and Kanban, Phase Plan, and Current Work views were verified with zero project items.
- [ ] Create initial milestone structure
- [ ] Validate Phase 00 completion criteria

## Phase 01 — Virtualization & Network Design

- [ ] Document virtualization requirements and constraints
- [ ] Select and document hypervisor platform
- [ ] Define VM resources, virtual switching, and adapter design
- [ ] Select OPNsense or pfSense CE
- [ ] Finalize IP addressing and VLAN plan
- [ ] Document routing, NAT, firewall, and segmentation design
- [ ] Document management, user, server, IoT/infrastructure, guest, and remote/VPN networks
- [ ] Implement approved hypervisor and virtual networking design
- [ ] Deploy and configure firewall/router VM
- [ ] Test allowed routing, prohibited routing, Internet access, management restrictions, guest isolation, and firewall logging
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 02 — Windows Server / DC01

- [ ] Deploy `DC01` using Windows Server 2025 Evaluation
- [ ] Configure hostname and static IP
- [ ] Install and configure AD DS and DNS
- [ ] Create AD forest/domain
- [ ] Define OUs, users, groups, administrative accounts, and service-account strategy
- [ ] Configure password policy and initial Group Policies
- [ ] Validate AD health, DNS, authentication, membership, and GPO processing
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 03 — DC02 & Active Directory Replication

- [ ] Deploy `DC02` with static IP and domain membership
- [ ] Configure AD DS, DNS, and Global Catalog where appropriate
- [ ] Configure AD and DNS replication
- [ ] Configure Sites and Services and document replication topology
- [ ] Verify FSMO role placement and awareness
- [ ] Test DC01 outage and DC02 authentication/DNS continuity
- [ ] Restore DC01 and verify replication, DNS synchronization, and AD health
- [ ] Exercise and document `repadmin`, `dcdiag`, Event Viewer, DNS, and PowerShell troubleshooting
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 04 — DHCP, Group Policy & Windows Clients

- [ ] Configure DHCP scopes, options, and reservations
- [ ] Deploy and domain-join Windows client VM(s)
- [ ] Configure department and security Group Policies
- [ ] Validate DHCP, DNS, domain discovery/join, authentication, and GPO processing
- [ ] Exercise DHCP failure, incorrect DNS, broken GPO, and incorrect gateway scenarios
- [ ] Validate client authentication while DC01 is offline
- [ ] Complete Milestone 1 DC01 outage and DC02 authentication/DNS failover test
- [ ] Document DC01 recovery and Milestone 1 results
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 05 — Linux Foundation

- [ ] Select a suitable free Linux distribution and deploy `LINUX01`
- [ ] Configure SSH, users/groups, permissions, and sudo
- [ ] Practice systemd, packages, networking, logs, and scheduled tasks
- [ ] Configure Nginx and document TLS concepts
- [ ] Validate SSH, services, DNS, networking, logging, and firewall behavior
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 06 — Docker & Docker Compose

- [ ] Install and configure Docker
- [ ] Build and run approved container workloads
- [ ] Define approved Docker Compose workloads
- [ ] Configure container networks, volumes, environment settings, logging, and health checks
- [ ] Verify no secrets are committed in images, Compose files, Git, or examples
- [ ] Test lifecycle, persistence, networking, logging, and health behavior
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 07 — Observability

- [ ] Define monitoring, logging, alerting, and retention requirements
- [ ] Deploy Prometheus, Grafana, Alertmanager, and Loki
- [ ] Deploy Windows Exporter and Node Exporter
- [ ] Monitor DC01, DC02, Linux, Docker, firewall/network, and critical services where practical
- [ ] Configure dashboards, alert rules, notification paths, and logs
- [ ] Validate `Failure → Prometheus → Alert Rule → Alertmanager → Notification`
- [ ] Record architecture, configuration, failure tests, and sanitized evidence

## Phase 08 — ServiceNow IT Operations

- [ ] Establish eligible ServiceNow developer resources and PDI
- [ ] Configure incidents, problems, changes, requests, knowledge, and service catalog
- [ ] Configure ITAM for endpoints, servers, network equipment, applications, and licenses
- [ ] Configure CMDB baseline and service/application/infrastructure relationships
- [ ] Test core ITSM, ITAM, CMDB, and knowledge workflows
- [ ] Prepare and later validate Alertmanager-to-ServiceNow incident integration
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 09 — CRM

- [ ] Deploy SuiteCRM as the primary free CRM option
- [ ] Configure users, roles, permissions, accounts, contacts, leads, and opportunities
- [ ] Configure reports and dashboards
- [ ] Validate the lead-to-sale workflow
- [ ] Integrate email, monitoring, CMDB, authentication, APIs, and automation where appropriate
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 10 — Email Protocol Lab

- [ ] Design an internal-only email protocol lab
- [ ] Deploy an approved stack such as Postfix and Dovecot
- [ ] Configure SMTP, IMAP, POP3, TLS, authentication, DNS, MX, and mail routing
- [ ] Test protocol behavior and troubleshooting scenarios
- [ ] Verify insecure mail services are not publicly exposed
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 11 — Microsoft Cloud Identity

- [ ] Confirm Microsoft developer/trial eligibility and licensing constraints
- [ ] Configure Microsoft 365 and Entra ID where eligible
- [ ] Configure and test users, groups, SSO, MFA, RBAC, and identity lifecycle
- [ ] Document hybrid identity concepts and on-premises AD relationship
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 12 — Intune / MDM / Endpoint Management

- [ ] Confirm Intune licensing and lab capabilities
- [ ] Configure device enrollment and Windows management where permitted
- [ ] Document iOS/iPadOS, Android, MDM, MAM, and BYOD controls
- [ ] Configure compliance, application deployment, and security policies where permitted
- [ ] Test lost-device lock/wipe and asset-update workflow where permitted
- [ ] Test non-compliant-device access blocking where permitted
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 13 — Remote Workforce

- [ ] Finalize remote-access requirements for five remote employees
- [ ] Select and configure WireGuard or OpenVPN Community Edition where appropriate
- [ ] Apply MFA, identity, endpoint compliance, and firewall controls where permitted
- [ ] Test connectivity, DNS, authorized internal access, denied unauthorized access, account disablement, and logging
- [ ] Create remote-access operational and troubleshooting runbooks
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 14 — Security Operations

- [ ] Define layered security controls and validation scenarios
- [ ] Apply least privilege, RBAC, MFA, segmentation, and firewall hardening
- [ ] Apply Defender, Intune compliance, Conditional Access, Windows security, auditing, and event logging where permitted
- [ ] Document TLS, certificate, service-account, and privileged-account controls
- [ ] Evaluate Wazuh only if justified
- [ ] Exercise authentication, endpoint, VLAN, lost-device, disabled-user, and expired-certificate scenarios
- [ ] Record architecture, configuration, incident/change records, tests, and sanitized evidence

## Phase 15 — Backup & Disaster Recovery

- [ ] Define RPO, RTO, retention, frequency, locations, and recovery priority
- [ ] Select appropriate free/community and native backup methods
- [ ] Configure backups for critical systems and configurations
- [ ] Test deleted-file and CRM/database restores
- [ ] Test failed-VM and domain-controller recovery
- [ ] Test configuration and monitoring-system recovery
- [ ] Create disaster recovery and restore runbooks
- [ ] Record recovery results, gaps, and sanitized evidence

## Phase 16 — Automation

- [ ] Identify and document manual workflows before automation
- [ ] Build approved PowerShell automation
- [ ] Build approved Python automation
- [ ] Integrate REST, JSON, OAuth 2.0, Microsoft Graph, ServiceNow, and CRM APIs where required
- [ ] Test onboarding, offboarding, computer provisioning, password, access, and audit workflows where appropriate
- [ ] Progress toward the approved ServiceNow-to-identity/application workflow
- [ ] Record scripts, tests, rollback guidance, and sanitized evidence

## Phase 17 — Azure & Infrastructure as Code

- [ ] Define Azure requirements and architecture
- [ ] Establish budgets, cost alerts, cost awareness, and cleanup procedures before deployment
- [ ] Select Terraform and/or OpenTofu
- [ ] Provision approved resources with IaC where practical
- [ ] Validate plans, deployments, repeatability, monitoring, and cleanup
- [ ] Document hybrid-network concepts and prevent undocumented cloud sprawl
- [ ] Record architecture, configuration, tests, and sanitized evidence

## Phase 18 — GitHub Actions / CI/CD

- [ ] Identify existing workflows that benefit from CI/CD
- [ ] Configure applicable PowerShell linting and Python tests
- [ ] Configure applicable Terraform validation/plan
- [ ] Configure documentation and PlantUML validation
- [ ] Configure applicable container builds and security scanning
- [ ] Test workflow success, failure, permissions, and secret handling
- [ ] Record configuration, tests, and sanitized evidence

## Phase 19 — Citrix / Application Delivery

- [ ] Confirm business value and available licensing/evaluation resources
- [ ] Select appropriate Citrix learning resources and/or XenServer
- [ ] Design an application-delivery or VDI lab if justified
- [ ] Integrate identity and remote-user access where permitted
- [ ] Test application delivery, access controls, and continuity concepts
- [ ] Record architecture, licensing, configuration, tests, and sanitized evidence

## Phase 20 — Kubernetes

- [ ] Verify Linux, Docker, Compose, networking, storage, TLS, observability, and troubleshooting prerequisites
- [ ] Define an approved Kubernetes architecture and use case
- [ ] Deploy an approved Kubernetes lab
- [ ] Configure Pods, Deployments, Services, Ingress, ConfigMaps, Secrets, storage, scaling, and health checks
- [ ] Integrate Kubernetes with Prometheus and Grafana
- [ ] Evaluate later OpenTelemetry, Loki, and Tempo extensions
- [ ] Test workload health, recovery, scaling, persistence, and troubleshooting
- [ ] Record architecture, configuration, tests, and sanitized evidence
