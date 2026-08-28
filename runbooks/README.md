# Runbook Standard

This directory contains repeatable operational, maintenance, troubleshooting, recovery, and escalation procedures. Runbooks describe approved ways to operate an established system; they do not approve architecture or silently replace an ADR, requirement, change record, or roadmap dependency.

## Identifiers and Files

- Use stable IDs `RUN-NNN`, beginning with `RUN-001` for the first real runbook.
- `RUN-000` is reserved for `RUN-000-template.md`; it is not an operational procedure.
- Use `RUN-NNN-short-kebab-case-title.md`. Never renumber or reuse an ID.
- Update a runbook when the same procedure changes. Preserve material history in Git and record review history in the document.

## Required Content

Use `RUN-000-template.md`. Each runbook defines its purpose, scope, owner role, related requirements and systems, phase, prerequisites, authorization/permissions, safety considerations, procedure, verification, rollback/recovery, troubleshooting, escalation, evidence produced, dependencies, and maintenance/review history.

Commands and steps must identify expected results and safe stopping points. Privileged, destructive, security-sensitive, or outage-producing steps require explicit authorization, exact scope, safeguards, and recovery guidance. A runbook must not embed credentials or assume unrestricted privilege.

## Lifecycle and Traceability

A runbook may be drafted before implementation but must be labeled accurately and cannot be treated as operationally validated until its procedure and recovery path are tested where applicable. Link existing `REQ-###`, roadmap phases, `ADR-###`, GitHub issues, `CHG-###`, `INC-###`, `TEST-###`, and `EVID-###` records as relevant. Use `None` or `TBD` rather than inventing links.

Review runbooks after material changes, incidents, failed tests, recovery exercises, or superseding ADRs. This public repository uses synthetic/sample values only; never commit secrets, recovery keys, live credentials, sensitive operational data, or unsanitized output.
