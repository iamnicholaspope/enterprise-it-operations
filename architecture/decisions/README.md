# Architecture Decision Records

> **Baseline approval:** The project owner approved this ADR framework and `ADR-000-template.md` as the current Phase 00 baseline on 2026-08-28. Git-backed baseline evidence begins with commit `b52bfc18c728e29fe466fc493958d35e49313909`.

This directory contains Architecture Decision Records (ADRs) for significant technical and design choices in the Enterprise IT Operations Lab.

ADRs explain why an architecture choice was made, which requirements and risks it affects, what alternatives were considered, and what must be implemented, tested, evidenced, and documented. Creating or accepting an ADR does not by itself complete implementation.

## Authority and Governance

- `docs/master-build-roadmap.md` remains authoritative for overall phase numbering, phase order, project dependencies, milestone sequencing, and completion criteria.
- An **Accepted** ADR becomes authoritative only for its stated decision scope.
- An ADR must not silently override a business requirement, the approved charter, or the master roadmap.
- If a requirement must change, update it through the explicit requirements/governance process and record the relationship in the ADR.
- If an Accepted ADR changes represented architecture, update the relevant PlantUML source under `architecture/diagrams/`.
- Link relevant risks from `docs/risk-register.md`; security and cost/licensing consequences must be reviewed before acceptance.
- Keep Deprecated, Rejected, and Superseded ADRs as historical records. Do not silently rewrite or delete their prior decisions.

## Information Classification

Use these labels inside ADRs whenever a statement’s authority could otherwise be unclear:

- **FACT:** Established by approved project documentation. Cite the source.
- **ASSUMPTION:** Temporarily treated as true but still requiring validation. Identify how or when it will be validated.
- **PROPOSAL:** A candidate design that has not received approval.
- **DECISION:** An explicitly approved architecture choice within a defined scope.

A proposal shown in a roadmap or diagram remains a proposal until an ADR or other authorized governance record explicitly approves it. For example, proposed network values and unresolved platform choices must not be treated as decisions.

## Identifier and Filename Convention

- `ADR-000` is reserved for `ADR-000-template.md` and is never a decision.
- Actual decisions begin at `ADR-001` and increment sequentially.
- IDs are stable: never renumber or reuse an ID, including after rejection or supersession.
- Use filenames in the form `ADR-NNN-short-kebab-case-title.md`.
- The filename should remain stable after creation unless correcting an obvious clerical error.

Illustrative filenames only—the following are not created or approved decisions:

- `ADR-001-hypervisor-selection.md`
- `ADR-002-firewall-platform.md`
- `ADR-003-active-directory-domain-design.md`

Before assigning an ID, inspect this directory and use the next unused number.

## Supported Statuses

- **Proposed:** The decision need, context, constraints, and options are under review. No architecture choice is authorized.
- **Accepted:** The project owner explicitly approved the decision. It is authoritative for its documented scope and may proceed through roadmap-controlled implementation.
- **Rejected:** The proposal was considered but not approved. Preserve the record and rationale; do not implement it as an accepted decision.
- **Deprecated:** The decision is still part of project history but is discouraged or scheduled for retirement. State what remains in effect and the transition plan.
- **Superseded:** A later Accepted ADR replaces the decision. Link both ADRs using `Supersedes` and `Superseded by`; preserve the old record.

Status changes require a dated entry in the ADR decision record. Only explicit project-owner approval can move a Proposed ADR to Accepted or Rejected. A later accepted ADR normally moves the replaced ADR to Superseded.

## ADR Lifecycle

``` text
Need identified
    ↓
ADR proposed
    ↓
Options evaluated
    ↓
Security / cost / licensing / operations reviewed
    ↓
Project-owner decision
    ↓
Accepted or Rejected
    ↓
Implementation (Accepted only, in roadmap order)
    ↓
Testing
    ↓
Evidence
    ↓
ADR remains Accepted or is later Superseded
```

1. Identify a decision whose scope and consequences justify an ADR.
2. Copy `ADR-000-template.md`, assign the next ID, and set status to Proposed.
3. Separate facts, assumptions, proposals, and decisions; cite governing sources.
4. Evaluate reasonable options against requirements, risks, constraints, security, licensing/cost, operations, dependencies, reversibility, testing, and documentation impact.
5. Obtain relevant technical, security, cost/licensing, and operational review.
6. Obtain an explicit project-owner decision and record the date, role, rationale, and evidence.
7. For Accepted ADRs, create or link implementation tasks/changes and proceed only when roadmap prerequisites are satisfied.
8. Test and capture evidence; update diagrams, runbooks, traceability, risks, and other affected documentation.
9. If the architecture later changes, create a new ADR and link the historical decision rather than rewriting it silently.

## When an ADR Is Required

Create an ADR for a decision with significant scope, long-lived consequences, meaningful alternatives, cross-system effects, security/cost/licensing implications, or difficult reversal. Typical examples include:

- hypervisor selection;
- firewall/router platform;
- network and VLAN architecture;
- Active Directory domain design;
- identity naming conventions;
- cloud identity architecture;
- VPN and remote-access architecture;
- monitoring architecture;
- backup architecture;
- significant security architecture;
- major application or platform selection; and
- a major deviation from the master roadmap.

A major roadmap deviation may also require explicit governance or requirements changes; an ADR alone cannot authorize it.

## When an ADR Is Not Normally Required

An ADR is not normally needed for:

- routine implementation steps within an Accepted architecture;
- minor configuration changes without architectural consequences;
- troubleshooting notes;
- individual incidents;
- standard operating procedures;
- test records or evidence; or
- tasks already dictated by an Accepted ADR.

Use tasks, configuration notes, change records, incident records, tests, evidence, or runbooks for those artifacts. Escalate to an ADR if a seemingly minor change alters a significant constraint, trust boundary, dependency, platform, cost/licensing model, or long-term operating approach.

## Review and Acceptance Checklist

Before an ADR becomes Accepted, confirm that:

- the decision is required now and its scope is clear;
- related requirement IDs, risk IDs, and phases are valid;
- facts, assumptions, proposals, and the decision are distinguishable;
- reasonable options and maintaining the current state were considered where applicable;
- security implications were reviewed;
- free/open-source, developer, evaluation/trial, and paid production licensing implications were classified accurately;
- operational, dependency, rollback, testing, documentation, and evidence effects were addressed;
- the decision does not silently override a requirement or roadmap dependency;
- the project owner explicitly approved the selected option; and
- affected PlantUML and governance artifacts are identified for update.

## Superseding, Deprecating, and Rejecting ADRs

- Do not edit historical rationale to make an old decision appear different.
- Create a new ADR for a replacement architecture choice.
- In the new ADR, populate `Supersedes`; in the old ADR, populate `Superseded by` and change its status to Superseded.
- Use Deprecated when a decision is being retired but has not yet been fully replaced.
- Use Rejected for a proposal that never became authoritative.
- Retain all records in source history and update relevant diagrams, tasks, risks, changes, tests, evidence, and runbooks to reflect the current state.

## Template

Use `ADR-000-template.md`. Do not treat the template, its placeholders, or illustrative filenames as architecture decisions.
