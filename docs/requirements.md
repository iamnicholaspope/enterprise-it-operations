# Requirements Register

> **Baseline approval:** The project owner approved the current requirements register, including `REQ-013` and `REQ-014`, on 2026-08-28. This accepts the requirements as governance inputs; it does not mean they are implemented or validated. Implementation and validation statuses remain authoritative in this register and `docs/requirements-traceability-matrix.md`.

| ID | Requirement | Priority | Status |
|---|---|---|---|
| REQ-001 | Employees must authenticate through centralized identity | Must | Planned |
| REQ-002 | The environment must use redundant Active Directory domain controllers | Must | Planned |
| REQ-003 | Remote employees must securely access corporate resources | Must | Planned |
| REQ-004 | IT must monitor server and application health | Must | Planned |
| REQ-005 | Lost or non-compliant managed devices must be remotely controlled | Must | Planned |
| REQ-006 | IT must track hardware and software assets | Must | Planned |
| REQ-007 | IT must manage incidents, problems, changes, and requests | Must | Planned |
| REQ-008 | Critical systems must be backed up and tested for recovery | Must | Planned |
| REQ-009 | New employee onboarding should be automated where practical | Should | Planned |
| REQ-010 | Infrastructure changes must be documented and testable | Must | In Progress |
| REQ-011 | Architecture must be documented in PlantUML | Must | In Progress |
| REQ-012 | Cloud resources should be provisioned with IaC where practical | Should | Planned |
| REQ-013 | The business must centrally manage customer, account, contact, and sales-opportunity information with role-appropriate access | Must | Planned |
| REQ-014 | Employees must have an organization-managed business messaging and communication capability with role-appropriate access | Must | Planned |

## Requirement and Technology Classification

Requirements describe business or system outcomes. They do not mandate a product merely because a technology appears in the roadmap.

- An **enabling dependency** supplies infrastructure needed by one or more requirements but is not itself a business outcome. General networking, routing, segmentation, and firewall capability are enabling dependencies; products, VLANs, and addressing remain architecture decisions.
- An **enabling platform / learning objective** may host or inform approved services while also developing portfolio capability. Linux and Docker are not mandatory business requirements and require later workload justification.
- A **learning / enabling workstream** develops transferable operational knowledge without defining the production solution. The Phase 10 email protocol lab does not require self-hosted email and does not by itself satisfy `REQ-014`.
- A **conditional / advanced learning platform** proceeds only after prerequisites and an appropriate workload/use case are justified. Kubernetes is not a mandatory business outcome, and omitting it does not fail the simulated company's mandatory requirements.

CRM and business messaging are approved business capabilities under `REQ-013` and `REQ-014`. Their platforms remain unresolved architecture/licensing decisions.

## Traceability Standard

Every major requirement should eventually map to:

Requirement → Architecture → Implementation → Test → Evidence
