# Testing Standard

This directory contains reproducible test plans and execution records used to verify implementations and support requirement validation. A test result and a requirement validation status are separate: a test can pass while its related requirement remains `Not Validated` because other implementation, tests, evidence, or operational documentation are incomplete.

## Identifiers and Files

- Use stable IDs `TEST-NNN`, beginning with `TEST-001` for the first real test.
- `TEST-000` is reserved for `TEST-000-template.md`; it is never an executed test.
- Use `TEST-NNN-short-kebab-case-title.md`. Never renumber or reuse an ID.
- One record may be revised for retries of the same test objective. Create a new ID when the objective or tested control materially changes.

## Statuses

- **Planned:** Purpose and intended coverage are recorded, but prerequisites may be incomplete.
- **Ready:** Prerequisites, environment, procedure, expected result, and safety controls are complete enough to execute.
- **Passed:** The recorded actual result meets the expected result and supporting evidence is linked where applicable.
- **Failed:** The actual result does not meet the expected result.
- **Blocked:** Execution cannot proceed because a stated dependency or condition is unavailable.
- **Retest Required:** A prior result is no longer sufficient because of remediation, material change, invalid evidence, or an incomplete recovery check.

Status describes the latest execution state, not requirement validation. The RTM uses `Not Validated`, `Partially Validated`, `Validated`, or `Failed` independently.

## Required Content and Lifecycle

Use `TEST-000-template.md`. Define purpose, related `REQ-###` values, roadmap phase, GitHub issue/change/ADR links where applicable, prerequisites, environment, safety limits, procedure, expected result, and evidence expectations before execution. After execution, record actual result, status, evidence, troubleshooting, retest conditions, and validation outcome.

Tests involving intentional failure or security weakness must define isolation, rollback, and post-test safety validation before execution. Never report `Passed` without reproducible actual results. Preserve prior execution history when retesting rather than silently rewriting it.

## Traceability and Security

Link only existing requirements, risks, ADRs, issues, changes, incidents, evidence, and runbooks. Use `None` or `TBD` when no valid artifact exists. Evidence belongs under `evidence/` or in an approved external location and must follow `evidence/README.md`.

This is a public repository. Use synthetic/sample data only. Never commit passwords, tokens, private keys, recovery keys, live credentials, secret-bearing output, sensitive personal information, or unsanitized logs/screenshots.
