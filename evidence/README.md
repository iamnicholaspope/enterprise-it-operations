# Evidence Standard

This directory contains or indexes artifacts that support reproducibility and verification of implementation, testing, troubleshooting, recovery, Git/GitHub governance, and requirement satisfaction. Evidence is supporting material, not proof by existence: a screenshot or log is useful only when its source, purpose, context, result, and relationship to the tested claim are clear.

## Categories

Approved categories include configuration output, command output, screenshots, logs, exported configuration, monitoring evidence, test results, recovery evidence, and Git/GitHub evidence. Store text-based, reviewable artifacts in Git where practical; large, binary, volatile, or externally retained artifacts should be indexed by a metadata record rather than committed blindly.

## Identifiers and Naming

- Use stable IDs `EVID-NNN`, beginning with `EVID-001` for the first real evidence record.
- `EVID-000` is reserved for `EVID-000-template.md`; it is not captured evidence.
- Metadata record: `EVID-NNN-short-kebab-case-title.md`.
- Associated sanitized files: `EVID-NNN-short-title.ext`, or a subdirectory named `EVID-NNN-short-title/` when several files form one evidence set.
- Never renumber or reuse an ID. Do not overwrite materially different evidence; allocate a new ID and link the replacement.

## Required Context

Use `EVID-000-template.md` to record category, related requirement, test, phase, issue/change/incident/ADR where applicable, capture date, source/system, capture method, purpose, summary, storage reference, sanitization review, and integrity/context notes. Integrity notes should explain relevant transformations, truncation, redaction, time context, and how the artifact can be reproduced or independently checked. Use a checksum when it adds meaningful value; a checksum alone does not establish truth or completeness.

## Public-Repository Security

Before commit or publication, review every artifact and its metadata. Never store passwords, access/API tokens, private keys, private-key certificates, recovery keys, live credentials, secret-bearing configuration, sensitive personal information, or real customer/business records. Screenshots, logs, exports, and command output require explicit review for usernames, email addresses, host details, URLs, tokens, session data, browser chrome, and local paths. Redact or regenerate safely; do not rely on cropping when hidden data may remain embedded.

Use only synthetic/sample values. If safe sanitization would make evidence misleading, do not publish the artifact; record an honest metadata-only reference and access limitation instead.

## Traceability and Validation

Link only artifacts that exist. A test should cite its evidence IDs, and the RTM should cite evidence only when it actually supports the requirement. Evidence does not make a failed test pass, does not make an implementation complete, and does not independently make a requirement `Validated`.
