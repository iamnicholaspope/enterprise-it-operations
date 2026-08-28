# Change Record Standard

This directory contains controlled records for material modifications to the lab environment or its governed configuration. A change record authorizes and records implementation; an ADR decides significant architecture. Neither replaces the other.

## When a Formal Change Is Appropriate

Use a formal change record when work can materially affect service, security, data, shared configuration, architecture implementation, cost/licensing exposure, recovery, or multiple components; requires approval or a maintenance window; introduces meaningful rollback needs; or implements an accepted ADR. Routine, low-risk documentation edits and ordinary task steps may remain documented through their GitHub issue, Git commit, test, and evidence when no operational state or governed configuration changes. Escalate uncertain work to a formal change rather than understating risk.

## Identifiers and Files

- Use stable IDs `CHG-NNN`, beginning with `CHG-001` for the first real change.
- `CHG-000` is reserved for `CHG-000-template.md`; it is never requested, approved, implemented, or completed work.
- Use `CHG-NNN-short-kebab-case-title.md`. Never renumber or reuse an ID.

## Lifecycle

Suggested states are **Draft**, **Proposed**, **Approved**, **Scheduled**, **In Progress**, **Implemented**, **Validated**, **Failed**, **Rolled Back**, **Cancelled**, and **Closed**. Use only states supported by the recorded facts. Approval must identify the approving role and date; a template or proposal is not approval.

Use `CHG-000-template.md` to record the change ID/title, status, owner, requirements, risks, ADRs, phase, GitHub issue, affected systems, justification, scope, risk assessment, prerequisites, implementation plan, validation plan, rollback plan, maintenance window if applicable, approvals, implementation result, tests, evidence, incidents, documentation impact, and follow-up actions.

## Traceability and Security

Link only existing IDs and files. Accepted ADRs remain authoritative for their decision scope, while the master roadmap controls phase order. After implementation, record actual results separately from the plan and update affected diagrams, tests, evidence, runbooks, RTM entries, and incidents where applicable.

This public repository uses synthetic/sample values only. Never commit credentials, secrets, private keys, recovery keys, sensitive operational exports, or unsanitized logs. Plans must avoid exposing a usable attack path or secret-bearing rollback material.
