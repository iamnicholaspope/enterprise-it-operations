# Project Context

## Business Scenario

This project models a 26-employee hybrid business:

- 21 office employees
- 5 remote employees
- One primary office
- Hybrid on-premises/cloud environment

## Goal

Build a realistic enterprise IT environment that demonstrates business-impacting experience rather than disconnected technology demos.

Every major technology should solve a documented business requirement and progress through:

Learn → Build → Configure → Integrate → Break → Troubleshoot → Automate → Test → Document

## Major Domains

- Windows Server / Active Directory
- DNS / DHCP / Group Policy
- AD replication with DC01 and DC02
- Networking, VLANs, firewalling, VPN
- Microsoft 365 / Entra / Intune / Defender
- MDM / UEM
- ServiceNow ITSM / ITAM / CMDB
- CRM
- SMTP / IMAP / POP3
- Linux
- Docker / Docker Compose
- Prometheus / Grafana / Loki / Alertmanager
- Azure
- Terraform / OpenTofu
- PowerShell / Python / REST APIs
- Backup and disaster recovery
- Security and endpoint management
- Citrix / XenServer in a later phase
- Kubernetes in a later phase

## Architecture Principles

- PlantUML is the required diagramming format.
- Prefer free/open-source technologies where practical.
- Keep evaluation/trial licensing separate from permanent free licensing.
- Do not expose unfinished infrastructure publicly.
- Do not expose Domain Controllers directly to the Internet.
- Do not commit secrets.
- Tie technology choices to business requirements.
- Require testing and evidence before marking work complete.

## Resume Evidence Standard

A technology is not resume-ready merely because it was installed.

Meaningful evidence should include configuration, integration, troubleshooting, testing, automation where appropriate, and documentation.
