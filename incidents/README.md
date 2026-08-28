# Incident Record Standard

This directory contains records of observed or deliberately simulated unplanned service degradation, failure, or security events. Do not invent completed incidents. Clearly label exercises and simulations, and record only events that actually occurred in the lab.

## Record Types

- **Incident:** An unplanned service degradation, failure, or security event requiring response and restoration.
- **Problem:** The underlying cause, or suspected cause, requiring deeper analysis beyond immediate restoration. Issue #1 does not establish a separate Problem Management template.
- **Change:** A controlled modification to the environment, including remediation implemented through `changes/` when formal change control is appropriate.

An incident may lead to a problem investigation and one or more changes, but the records remain distinct and cross-linked.

## Identifiers and Files

- Use stable IDs `INC-NNN`, beginning with `INC-001` for the first real incident.
- `INC-000` is reserved for `INC-000-template.md`; it is not a real or simulated incident.
- Use `INC-NNN-short-kebab-case-title.md`. Never renumber or reuse an ID.

## Lifecycle and Required Content

Suggested states are **Open**, **Investigating**, **Monitoring**, **Resolved**, and **Closed**. Resolution restores or contains service; closure requires required validation, evidence, and follow-up disposition.

Use `INC-000-template.md` to record ID/title, state, detected and reported times, source/reporter role, affected service/system, requirements, risks, phase, GitHub issue, severity/priority, symptoms, business/technical impact, detection method, timeline, troubleshooting, root cause if known, containment, resolution, recovery validation, tests, evidence, related problem/change, lessons learned, follow-up actions, and review/closure.

Preserve the event chronology and distinguish observed facts from hypotheses. Unknown root cause must remain `Unknown` rather than being inferred.

## Traceability and Security

Link only existing `REQ-###`, `RISK-###`, `ADR-###`, GitHub issues, `CHG-###`, `TEST-###`, `EVID-###`, and runbooks. If a risk is realized, link the incident from the risk register when governance review determines that update is warranted.

This repository is public and all scenarios/data must be synthetic. Never commit passwords, tokens, private keys, recovery keys, live credentials, sensitive personal information, exploit-ready secrets, or unsanitized logs/screenshots. Security exercises must record containment and post-event safety validation.
