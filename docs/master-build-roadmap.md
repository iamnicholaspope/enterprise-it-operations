# Enterprise IT Operations Lab --- Master Build Roadmap

## Purpose

This document is the authoritative implementation sequence for the
Enterprise IT Operations Lab.

The project models the IT environment of a hypothetical 26-employee
business:

-   21 office employees
-   5 remote employees
-   One primary office
-   Hybrid on-premises/cloud infrastructure
-   Centralized IT operations
-   Secure remote workforce
-   Modern monitoring, endpoint management, automation, and disaster
    recovery

Individual project phases may be completed in separate AI chats.

Every chat working on this project must use this roadmap to determine:

1.  What phase is currently active.
2.  What dependencies must already exist.
3.  What work is in scope.
4.  What work must not yet be implemented.
5.  What evidence is required before the phase is considered complete.

------------------------------------------------------------------------

# Project Execution Rule

The project must be built incrementally.

The standard lifecycle for every significant component is:

``` text
Business Requirement
        ↓
Architecture
        ↓
Implementation
        ↓
Configuration
        ↓
Integration
        ↓
Testing
        ↓
Failure Testing
        ↓
Troubleshooting
        ↓
Evidence
        ↓
Documentation
        ↓
Complete
```

Installing software does NOT make a task complete.

A technology becomes project-complete only after the required
configuration, testing, evidence, and documentation have been completed.

------------------------------------------------------------------------

# AI Session Rules

At the beginning of every implementation chat, read:

1.  `AGENTS.md`
2.  `docs/project-context.md`
3.  `docs/master-build-roadmap.md`
4.  `docs/requirements.md`
5.  `docs/plan.md`
6.  `docs/tasks.md`
7.  Relevant ADRs
8.  Relevant PlantUML diagrams
9.  Relevant runbooks/testing documentation

Before implementing anything:

-   Identify the current phase.
-   Identify the requirement IDs being addressed.
-   Confirm dependencies are complete.
-   Identify affected files/documentation.
-   Do not implement future phases unless explicitly instructed.

At the end of each implementation session:

-   Update task status.
-   Update architecture if necessary.
-   Record configuration decisions.
-   Add/update tests.
-   Record evidence.
-   Document problems encountered.
-   Update runbooks where appropriate.
-   Update the traceability matrix.
-   Identify the next logical task.

------------------------------------------------------------------------

# PHASE 00 --- Project Governance

## Objective

Establish project controls before infrastructure deployment.

## Build

Create and maintain: - Git repository - `AGENTS.md` - Project context -
Project charter - Business profile - Requirements register - Master
roadmap - Task register - Risk register - Requirements traceability
matrix - ADR structure - Testing structure - Evidence structure -
Runbook structure - PlantUML architecture structure - GitHub
Project/Kanban board

## Required Documentation

``` text
docs/
├── project-context.md
├── master-build-roadmap.md
├── requirements.md
├── plan.md
├── tasks.md
├── roadmap.md
├── risk-register.md
└── project-charter.md
```

``` text
architecture/
├── diagrams/
└── decisions/
```

## Completion Criteria

-   Project purpose is documented.
-   Business scenario is documented.
-   Requirements have IDs.
-   Build phases are defined.
-   PlantUML is established as the diagramming standard.
-   Tasks can be traced to requirements.
-   AI agents have clear project instructions.

------------------------------------------------------------------------

# PHASE 01 --- Virtualization & Network Design

## Governance Classification

General networking, routing, segmentation, and firewall capability are **enabling dependencies** for centralized services, secure remote access, monitoring, endpoint/security controls, and hybrid/cloud integration. No vendor, VLAN scheme, or IP plan is a business requirement; those remain later architecture decisions.

## Objective

Create the infrastructure foundation on which all other systems depend.

## Implement

-   Hypervisor
-   Virtual networking
-   Firewall/router VM
-   OPNsense or pfSense CE
-   IP addressing
-   VLAN architecture
-   Routing
-   NAT
-   Firewall rules
-   Management network
-   Corporate-user network
-   Server network
-   Guest network
-   Remote/VPN network

## Proposed Network

``` text
10.10.0.0/16

VLAN 10 — Management       10.10.10.0/24
VLAN 20 — Corporate Users  10.10.20.0/24
VLAN 30 — Servers          10.10.30.0/24
VLAN 40 — IoT/Infrastructure 10.10.40.0/24
VLAN 50 — Guest            10.10.50.0/24
VLAN 60 — Remote/VPN       10.10.60.0/24
```

These values remain proposals until finalized during implementation.

## Learn

TCP/IP, IPv4, subnetting, VLANs, routing, NAT, firewall rules, network
segmentation, and troubleshooting.

## Test

-   Required VLAN routing works.
-   Prohibited VLAN routing fails.
-   Internet access works where intended.
-   Guest devices cannot access internal servers.
-   Management interfaces are appropriately restricted.
-   Firewall logging works.

## Evidence

Network architecture diagram, VLAN table, IP plan, firewall rules,
connectivity tests, and sanitized screenshots/config exports.

------------------------------------------------------------------------

# PHASE 02 --- Windows Server / DC01

## Objective

Create the primary Windows identity infrastructure.

## Implement

Deploy `DC01` with: - Windows Server 2025 Evaluation - Static IP -
Hostname - AD DS - DNS - Active Directory forest/domain - OU structure -
Users and groups - Security groups - Administrative accounts -
Service-account strategy - Password policy - Initial Group Policies

## Learn

Windows Server administration, AD DS, DNS, OUs, users/groups, Group
Policy, RBAC, and PowerShell.

## Test

AD health, DNS resolution, user creation, group membership,
authentication, and Group Policy processing.

------------------------------------------------------------------------

# PHASE 03 --- DC02 & Active Directory Replication

## Objective

Eliminate DC01 as a single point of failure and demonstrate AD
redundancy.

## Implement

Deploy `DC02` and configure: - Static IP - Domain membership - AD DS -
DNS - Global Catalog where appropriate - AD replication - DNS
replication - FSMO role awareness - Sites and Services - Replication
topology

## Required Failure Test

Shut down DC01 and verify domain authentication, DNS, and client
functionality continue through DC02. Restore DC01 and verify replication
resumes, AD health returns to normal, and DNS data synchronizes.

## Troubleshooting Exercises

Practice `repadmin`, `dcdiag`, DNS diagnostics, Event Viewer, and
PowerShell AD commands.

------------------------------------------------------------------------

# PHASE 04 --- DHCP, Group Policy & Windows Clients

## Objective

Create the managed corporate workstation environment.

## Implement

-   DHCP scopes/options/reservations
-   Windows client VM(s)
-   Domain joining
-   Group Policy
-   Department-based policies
-   Security policies
-   Drive/printer concepts where appropriate

## Test

Verify DHCP, DNS, domain discovery/join, authentication, GPO processing,
and client authentication while DC01 is offline.

## Failure Exercises

Stop DHCP, introduce incorrect DNS, break a GPO, and test incorrect
gateway configuration. Document diagnosis and recovery.

------------------------------------------------------------------------

# PHASE 05 --- Linux Foundation

## Governance Classification

Linux is an **enabling platform / learning objective**, not a mandatory business requirement. Deploy it only as the roadmap learning foundation or where a later approved service/architecture justifies it.

## Objective

Introduce Linux systems administration.

Deploy `LINUX01` using Ubuntu Server or another appropriate free Linux
distribution.

## Learn

SSH, Bash, users/groups, permissions, sudo, systemd, package management,
networking, logs, cron/systemd timers, Nginx, and TLS concepts.

## Test

SSH access, service management, DNS, networking, logging, and firewall
behavior.

------------------------------------------------------------------------

# PHASE 06 --- Docker & Docker Compose

## Governance Classification

Docker and containerization are an **enabling platform / learning objective**, not a mandatory business requirement. Container workloads must be tied to approved services and later architecture decisions.

## Objective

Establish the project's container platform.

## Implement

Docker, Docker Compose, container networks, persistent volumes,
environment configuration, and health checks.

## Learn

Images, containers, Dockerfiles, Compose, volumes, networks, environment
variables, lifecycle, logging, and health checks.

## Security

Never commit secrets into Dockerfiles, Compose files, Git, or
environment examples.

------------------------------------------------------------------------

# PHASE 07 --- Observability

## Objective

Create centralized infrastructure monitoring before adding many business
applications.

## Primary Stack

-   Prometheus
-   Grafana
-   Alertmanager
-   Loki
-   Windows Exporter
-   Node Exporter
-   Later: OpenTelemetry and Tempo

## Monitor

DC01, DC02, Linux hosts, Docker, CRM when deployed, network/firewall
where practical, and critical services.

## Required Failure Tests

Stop monitored services/hosts or safely trigger thresholds and verify:

``` text
Failure → Prometheus → Alert Rule → Alertmanager → Notification
```

Later integrate this with ServiceNow.

------------------------------------------------------------------------

# PHASE 08 --- ServiceNow IT Operations

## Objective

Create the operational IT management platform.

## Register

Create/use ServiceNow developer resources and a Personal Developer
Instance where available.

## Implement

ITSM: Incidents, Problems, Changes, Requests, Knowledge, Service
Catalog.

ITAM: laptops, desktops, mobile devices, servers, network equipment,
applications, software/licenses.

CMDB relationships:

``` text
Business Service → Application → Server → Database → Network
```

## Integrate

Eventually: `Prometheus → Alertmanager → ServiceNow → Incident`.

------------------------------------------------------------------------

# PHASE 09 --- CRM

## Governance Classification

Centralized customer and sales relationship management is a **business capability** under `REQ-013`. SuiteCRM is a proposed implementation option and is not prescribed by the requirement.

## Objective

Implement a business application supporting revenue/customer operations.

## Primary Free Option

SuiteCRM. Salesforce Trailhead may supplement CRM learning.

## Model

`Lead → Opportunity → Quote → Customer → Sale`

## Configure

Users, roles, permissions, accounts, contacts, leads, opportunities,
reports, and dashboards.

## Integrate

Email, monitoring, ServiceNow CMDB, authentication where appropriate,
APIs, and automation.

------------------------------------------------------------------------

# PHASE 10 --- Email Protocol Lab

## Governance Classification

This phase is a **learning / enabling workstream** for messaging protocols. It is not the required production messaging solution and does not mandate Postfix, Dovecot, SMTP, IMAP, POP3, or self-hosted email. An approved architecture in a later applicable phase may satisfy `REQ-014` through Microsoft 365/Exchange Online or another justified platform, subject to licensing.

## Objective

Understand traditional enterprise email infrastructure and protocols.

## Potential Stack

Postfix + Dovecot.

## Learn

SMTP, IMAP, POP3, TLS, authentication, DNS, MX records, mail routing,
and troubleshooting.

## Security

Keep the initial lab mail system internal. Do not expose insecure
SMTP/POP3 publicly.

------------------------------------------------------------------------

# PHASE 11 --- Microsoft Cloud Identity

## Governance Classification

Microsoft cloud identity is an enabling architecture for approved identity, access, endpoint, and communication outcomes where licensing permits. If Microsoft 365 messaging is selected later, it may satisfy `REQ-014`; this roadmap does not pre-approve that product or license.

## Objective

Extend traditional AD knowledge into modern Microsoft cloud identity.

## Register/Configure Where Eligible

Microsoft 365, Microsoft Entra ID, and appropriate developer/trial
environments.

## Learn

Users/groups, cloud identity, hybrid identity concepts, SSO, MFA, RBAC,
identity lifecycle, and Microsoft 365 administration.

Conceptually: `On-Prem AD → Entra ID → Microsoft 365`.

------------------------------------------------------------------------

# PHASE 12 --- Intune / MDM / Endpoint Management

## Objective

Manage company and BYOD endpoints, particularly the five remote
employees.

## Implement Where Licensing/Lab Access Permits

Intune, device enrollment, Windows management, iOS/iPadOS and Android
concepts, MDM, MAM, BYOD, compliance policies, app deployment, and
security configuration.

## Required Scenarios

Lost device:
`Device Lost → ServiceNow Incident → Review → Remote Lock/Wipe → Asset Update`.

Non-compliant device:
`Device → Intune → Compliance Failure → Conditional Access → Corporate Access Blocked`,
where licensing/functionality permits.

------------------------------------------------------------------------

# PHASE 13 --- Remote Workforce

## Objective

Securely support the five remote employees.

## Implement

Potentially WireGuard or OpenVPN Community Edition, MFA, Entra
authentication concepts, endpoint compliance, and firewall policies.

## Test

Remote connectivity, DNS, internal access, denied unauthorized access,
account disablement, and logging.

------------------------------------------------------------------------

# PHASE 14 --- Security Operations

## Objective

Apply layered security controls across the existing environment.

## Implement/Learn

Least privilege, RBAC, MFA, Conditional Access, segmentation, Defender,
Intune compliance, Windows security, firewall hardening, TLS,
certificate management, service/privileged accounts, auditing, and event
logs.

Optional free addition: Wazuh.

## Exercises

Failed login, locked account, suspicious authentication, non-compliant
endpoint, unauthorized VLAN access, lost device, disabled employee, and
expired certificate.

------------------------------------------------------------------------

# PHASE 15 --- Backup & Disaster Recovery

## Objective

Ensure critical business services can be recovered.

## Implement

Use free/community solutions where practical, including Veeam Community
Edition where appropriate, native Windows/Linux tooling, and
database-native backups.

## Define

RPO, RTO, retention, backup frequency, backup locations, and recovery
priority.

## Required Recovery Tests

Deleted file restore, CRM/database restore, failed VM recovery, DC
failure, configuration restore, and monitoring-system recovery.

A backup is not considered valid until a restore has been tested.

------------------------------------------------------------------------

# PHASE 16 --- Automation

## Objective

Automate processes already understood manually.

Do not automate a process before understanding and documenting its
manual workflow.

## PowerShell

Potential scripts: - `New-Employee.ps1` - `Disable-Employee.ps1` -
`Provision-Computer.ps1` - `Reset-UserPassword.ps1` -
`Get-UserAccess.ps1` - `Audit-ADAccounts.ps1`

## Python

Use for APIs, reporting, health checks, data processing, and
integration.

## APIs

REST, JSON, OAuth 2.0, Microsoft Graph, ServiceNow APIs, and CRM APIs.

## Target Workflow

`ServiceNow Request → Automation → AD → Entra/M365 → Groups/Permissions → Intune → CRM → Notification`.

------------------------------------------------------------------------

# PHASE 17 --- Azure & Infrastructure as Code

## Objective

Extend the environment into cloud infrastructure while learning
reproducible deployment.

## Before Deployment

Implement Azure cost awareness, budgets, cost alerts, and cleanup
procedures.

## Use

Azure and Terraform and/or OpenTofu.

## Potential Resources

Resource Groups, VNets, subnets, test VMs, storage, monitoring, and
hybrid-network concepts.

## Rule

Prefer IaC for repeatable cloud resources when practical. Avoid
undocumented manual cloud sprawl.

------------------------------------------------------------------------

# PHASE 18 --- GitHub Actions / CI/CD

## Objective

Introduce automated validation/deployment for engineering artifacts.

## Potential Uses

PowerShell linting, Python testing, Terraform validation/plan,
documentation checks, PlantUML validation, container builds, and
appropriate security scanning.

Use CI/CD only where it improves an existing workflow.

------------------------------------------------------------------------

# PHASE 19 --- Citrix / Application Delivery

## Objective

Explore enterprise remote application and VDI concepts.

## Potential Technologies

Citrix learning/evaluation resources and XenServer.

## Learn

Virtualization, application delivery, remote applications, VDI, identity
integration, remote-user access, and business continuity.

This phase is optional and dependent on available licensing/evaluation
resources.

------------------------------------------------------------------------

# PHASE 20 --- Kubernetes

## Governance Classification

Kubernetes is a **conditional / advanced learning platform**, not a mandatory business requirement. Execute this phase only after prerequisite container skills are complete and an appropriate workload/use case and architecture are approved. Its absence does not by itself fail a mandatory business requirement.

## Objective

Introduce container orchestration only after Docker fundamentals are
established.

## Prerequisites

Linux administration, Docker, Docker Compose, container networking,
persistent storage concepts, TLS concepts, Prometheus, Grafana, and
container troubleshooting.

## Learn

Pods, Deployments, Services, Ingress, ConfigMaps, Secrets, persistent
storage, scaling, and health checks.

## Integrate

`Kubernetes → Prometheus → Grafana`, later extending to OpenTelemetry,
Loki, and Tempo.

------------------------------------------------------------------------

# Overall Dependency Order

``` text
Project Governance
        ↓
Virtualization
        ↓
Network / Firewall
        ↓
DC01
        ↓
DC02 + AD Replication
        ↓
DHCP + GPO + Windows Clients
        ↓
Linux
        ↓
Docker
        ↓
Prometheus / Grafana / Loki
        ↓
ServiceNow
        ↓
CRM
        ↓
Email
        ↓
Microsoft 365 / Entra
        ↓
Intune / MDM
        ↓
Remote Workforce
        ↓
Security Operations
        ↓
Backup / DR
        ↓
Automation
        ↓
Azure / Terraform
        ↓
CI/CD
        ↓
Citrix
        ↓
Kubernetes
```

------------------------------------------------------------------------

# Milestone 1 --- First Major Technical Checkpoint

Do not rush into cloud, ServiceNow, CRM, or Kubernetes.

``` text
Firewall / Network
        ↓
DC01
        ↓
DC02
        ↓
AD Replication
        ↓
DNS
        ↓
DHCP
        ↓
Windows Client
        ↓
Group Policy
        ↓
DC01 Failure Test
        ↓
DC02 Authentication/DNS Failover
```

Milestone 1 succeeds when appropriate identity and DNS functionality
continue during a planned DC01 outage and recovery is documented.

------------------------------------------------------------------------

# Documentation Required Per Phase

## Architecture

-   `.puml` diagrams
-   ADRs
-   Network/system design

## Configuration

-   Configuration notes
-   Scripts
-   Sanitized configuration exports where appropriate

## Testing

-   Test ID
-   Objective
-   Prerequisites
-   Procedure
-   Expected result
-   Actual result
-   PASS/FAIL

## Evidence

Screenshots, command output, logs, dashboard screenshots, ServiceNow
records, and test results. Never include secrets.

## Operations

Where appropriate: runbook, troubleshooting guide, knowledge article,
incident record, and change record.

------------------------------------------------------------------------

# Definition of Done

A project task may only be marked `[x]` when applicable requirements are
satisfied:

-   Implementation completed.
-   Configuration documented.
-   Security considered.
-   Testing performed.
-   Test result recorded.
-   Failure scenario tested where appropriate.
-   Evidence captured.
-   PlantUML updated if architecture changed.
-   Runbook updated if operational procedure changed.
-   Requirement traceability updated.
-   No secrets committed.
-   Relevant Git changes committed.

Simply installing a technology is insufficient.

------------------------------------------------------------------------

# Cost Rule

The project should remain free or extremely low-cost wherever practical.

Prefer open-source software, community editions, developer environments,
official evaluation environments, and vendor learning sandboxes.

Always distinguish:

``` text
FREE / OPEN SOURCE
vs.
FREE DEVELOPER USE
vs.
TIME-LIMITED EVALUATION
vs.
PAID PRODUCTION LICENSE
```

Do not create paid cloud infrastructure without explicit approval.

------------------------------------------------------------------------

# Public Domain Rule

A real domain may eventually be used where it provides meaningful
experience.

However:

-   Domain Controllers must never be directly Internet-exposed.
-   Internal management interfaces must not be publicly exposed.
-   Lab SMTP/POP3 services must not be exposed insecurely.
-   TLS must be used for appropriate public services.
-   Public and internal DNS should be designed deliberately.
-   Secrets must never be stored in Git.
-   Internet-facing services require a documented security review before
    exposure.

------------------------------------------------------------------------

# Resume Rule

Do not add a technology to the résumé merely because it appears in this
roadmap.

A technology becomes résumé-ready after sufficient hands-on evidence
exists:

``` text
Learn
 ↓
Build
 ↓
Configure
 ↓
Integrate
 ↓
Break
 ↓
Troubleshoot
 ↓
Automate where appropriate
 ↓
Test
 ↓
Document
 ↓
Resume
```

The final project should support the truthful statement:

> Designed, implemented, secured, monitored, automated, and documented a
> hybrid enterprise IT environment for a simulated 26-employee
> organization with 21 office and 5 remote users, incorporating
> redundant Active Directory services, segmented networking, endpoint
> management, Microsoft cloud identity, ITSM/CMDB/ITAM, business
> applications, observability, backup/disaster recovery, automation,
> Infrastructure as Code, and modern DevOps practices.
