# ADR-000 — [Decision Title]

> **Template notice:** ADR-000 is reserved for this template. It is not an architecture decision. Copy this file, assign the next unused ADR ID, replace every bracketed instruction, and remove this notice.

> **Template baseline approval:** The project owner approved this template as part of the current Phase 00 ADR-framework baseline on 2026-08-28. Git-backed baseline evidence begins with commit `b52bfc18c728e29fe466fc493958d35e49313909`. This approval does not approve any architecture choice.

## Metadata

| Field | Value |
|---|---|
| ADR ID | `ADR-[NNN]` |
| Title | [Concise decision title] |
| Status | Proposed |
| Date | [YYYY-MM-DD] |
| Decision owner | [Accountable owner role] |
| Related requirements | [`REQ-###`, or `None`] |
| Related risks | [`RISK-###`, or `None`] |
| Related phases | [Phase number and authoritative name] |
| Related ADRs | [`ADR-###`, or `None`] |
| Supersedes | [`ADR-###`, or `None`] |
| Superseded by | [`ADR-###`, or `None`] |

## Information Classification

Label material statements used by this ADR so readers can distinguish their authority:

- **FACT:** [Established by approved project documentation; cite the source.]
- **ASSUMPTION:** [Temporarily treated as true; state owner and validation needed.]
- **PROPOSAL:** [Candidate design not yet approved.]
- **DECISION:** [Populate only after explicit approval; state approver and approval date.]

## Context

[Describe the business and technical context. Cite approved facts, requirements, roadmap constraints, relevant diagrams, and risks. Do not present proposals or assumptions as facts.]

## Problem / Decision Being Made

[State the specific architecture question and decision boundary. Explain why a decision is required now.]

## Constraints

[List applicable business, security, cost, licensing, operational, sequencing, resource, and compatibility constraints.]

## Considered Options

### Option 1 — [Name]

- **Summary:** [Candidate approach]
- **Benefits:** [Benefits]
- **Drawbacks / tradeoffs:** [Drawbacks]
- **Security considerations:** [Security effects]
- **Cost/licensing considerations:** [Classify free/open source, free developer use, time-limited evaluation/trial, or paid production licensing where relevant]
- **Operational considerations:** [Support, monitoring, backup, recovery, skills, and lifecycle effects]
- **Requirement and risk effects:** [Relevant IDs]

### Option 2 — [Name]

- **Summary:** [Candidate approach]
- **Benefits:** [Benefits]
- **Drawbacks / tradeoffs:** [Drawbacks]
- **Security considerations:** [Security effects]
- **Cost/licensing considerations:** [Licensing classification and effects]
- **Operational considerations:** [Operational effects]
- **Requirement and risk effects:** [Relevant IDs]

[Add other viable options, including retaining the current state when appropriate. Do not add token options merely to create a longer list.]

## Decision

**DECISION:** [For a Proposed ADR, write `Pending project-owner decision`. For an Accepted ADR, state the explicitly approved choice and its scope. For Rejected, Deprecated, or Superseded ADRs, preserve the historical decision text and explain status changes elsewhere.]

## Rationale

[Explain why the selected option best satisfies the approved requirements and constraints. If no option is accepted, explain why.]

## Security Implications

[Describe trust boundaries, access control, exposure, secrets, hardening, logging, vulnerability, failure-testing, and recovery implications. Link relevant risks.]

## Cost and Licensing Implications

[Describe cost controls and distinguish free/open source, free developer use, time-limited evaluation/trial, and paid production licensing. Do not invent a budget or imply production rights from lab access.]

## Operational Implications

[Describe administration, support, monitoring, alerting, backup, recovery, maintenance, patching, skills, and troubleshooting implications.]

## Dependencies

[List prerequisite phases, systems, decisions, approvals, licensing, or external services. The master roadmap remains authoritative for overall phase order and project dependencies.]

## Consequences

### Positive Consequences

- [Positive result]

### Negative Consequences / Tradeoffs

- [Cost, limitation, complexity, risk, or lost alternative]

## Implementation Impact

[Identify affected components, tasks, scripts, configurations, migrations, and changes. Acceptance authorizes the decision scope, not untracked implementation outside the roadmap.]

## Testing and Validation Requirements

[Define tests, expected outcomes, failure scenarios, security validation, rollback validation, and acceptance evidence. Use formal test records where applicable.]

## Documentation Impact

[List PlantUML diagrams, architecture documents, tasks, requirements traceability, runbooks, changes, configuration notes, and other artifacts that must be updated.]

## Rollback / Reversal Considerations

[Describe whether and how the decision can be reversed, migration dependencies, data/configuration portability, and conditions that would trigger reconsideration.]

## Evidence

[Link approved review notes, test records, sanitized output, diagrams, cost/licensing research, change records, or other evidence. Never include secrets.]

## Decision Record

| Event | Date | Owner/approver role | Notes/evidence |
|---|---|---|---|
| Proposed | [YYYY-MM-DD] | [Role] | [Reason ADR was opened] |
| Reviewed | [YYYY-MM-DD or Pending] | [Roles] | [Security, cost/licensing, and operations review] |
| Decided | [YYYY-MM-DD or Pending] | Project Owner | [Accepted or Rejected decision and evidence] |
| Status changed | [YYYY-MM-DD or Not applicable] | [Role] | [Deprecated or Superseded rationale and links] |

## Follow-up

- [ ] Update affected PlantUML diagrams after acceptance and before dependent completion.
- [ ] Update requirements/governance explicitly if the approved business requirement must change.
- [ ] Update related risks and controls.
- [ ] Create or link implementation change/task records.
- [ ] Complete required testing and evidence.
- [ ] Update runbooks and operational documentation where applicable.
- [ ] Link any superseding or superseded ADR without deleting historical content.
