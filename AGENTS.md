# Enterprise IT Operations Lab — AI Instructions

## Project Purpose

This repository models a realistic IT environment for a hypothetical 26-employee company:

- 21 office employees
- 5 remote employees
- Hybrid on-premises/cloud infrastructure
- Free or low-cost technologies wherever practical

The project is intended to demonstrate resume-worthy hands-on experience with enterprise infrastructure, networking, identity, security, observability, ITSM, automation, cloud, endpoint management, and disaster recovery.

## Core Rule

Do not add technologies merely for exposure.

Every implementation must follow:

Business Requirement
→ Architecture
→ Implementation
→ Testing
→ Evidence
→ Documentation

## Before Starting Work

Before making any project changes, always read the following in order:

1. `docs/project-context.md`
2. `docs/master-build-roadmap.md`
3. `docs/requirements.md`
4. `docs/plan.md`
5. `docs/tasks.md`
6. Relevant architecture documentation
7. Relevant ADRs under `architecture/decisions/`
8. Relevant PlantUML diagrams under `architecture/diagrams/`
9. Relevant testing and runbook documentation

`docs/master-build-roadmap.md` is the authoritative source for project phase order, dependencies, milestone sequencing, and phase completion requirements.

Before implementing anything:

* Identify the current project phase.
* Identify the requirement IDs being addressed.
* Confirm prerequisite phases and dependencies are complete.
* Identify the task or tasks being worked on in `docs/tasks.md`.
* Identify any architecture, ADR, testing, runbook, or documentation files that may need to change.
* Do not implement future phases unless explicitly instructed.
* Do not begin implementation until the related requirement and task exist.

When working in a new or separate AI chat, first determine the current project state from the repository instead of assuming previous chat context.

At the end of each implementation session:

* Update task status in `docs/tasks.md`.
* Update architecture documentation if necessary.
* Update relevant PlantUML diagrams if architecture changed.
* Record important configuration decisions.
* Add or update tests.
* Record test results and evidence.
* Document problems and troubleshooting performed.
* Update runbooks where appropriate.
* Update the requirements traceability matrix where appropriate.
* Identify the next logical incomplete task.


## Task Management

Use `docs/tasks.md` as the source of truth for implementation progress.

- `[ ]` = not started
- `[~]` = in progress
- `[x]` = completed and validated
- `[!]` = blocked

Never mark a task complete merely because files were created.

A task is complete only after testing and documentation succeed.

## Architecture

PlantUML is the required diagramming format.

Architecture source files live under:

`architecture/diagrams/`

Do not replace PlantUML with Mermaid or another diagramming format unless explicitly requested.

Important architecture decisions belong under:

`architecture/decisions/`

Use ADRs for meaningful technology/design choices.

## Core Technologies

- Windows Server 2025
- Active Directory
- AD Replication
- DNS
- DHCP
- Group Policy
- PowerShell
- Linux
- OPNsense/pfSense
- WireGuard/OpenVPN
- Microsoft 365
- Microsoft Entra ID
- Microsoft Intune
- Microsoft Defender
- ServiceNow
- SuiteCRM
- SMTP / IMAP / POP3
- Prometheus
- Grafana
- Loki
- Alertmanager
- Docker
- Docker Compose
- Kubernetes (later phase)
- Azure
- Terraform/OpenTofu
- Git/GitHub
- GitHub Actions
- Python
- REST APIs

## Active Directory Requirement

The environment must use two domain controllers:

- DC01
- DC02

The project must demonstrate:

- AD replication
- DNS redundancy
- authentication failover
- FSMO roles
- replication troubleshooting
- Domain Controller recovery

## Security

Never commit:

- passwords
- API keys
- access tokens
- private keys
- production secrets

Do not expose Domain Controllers directly to the Internet.

Use least privilege, RBAC, MFA, segmentation, and secure defaults.

## Cost

Prefer free/open-source technologies.

Clearly identify technologies that rely on:

- Evaluation licenses
- Developer licenses
- Trials
- Paid production licenses

Do not create paid cloud resources unless explicitly approved.

## Documentation

Every significant implementation should update:

- relevant architecture documentation
- `docs/tasks.md`
- testing documentation
- relevant runbook
- README where appropriate

If implementation changes architecture, update the related `.puml` file.

## Scope Discipline

Do not implement future phases prematurely.

Follow the phase order, dependencies, milestone sequence, and completion criteria in `docs/master-build-roadmap.md`. Use `docs/plan.md` for the corresponding implementation summary.

Prefer small, reviewable changes.

Do not perform major refactors or reorganize directories without a documented reason.
