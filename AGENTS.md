# Research Knowledge Repository Constitution

## Purpose

Maintain public, sanitized, reviewed research knowledge and reusable metadata without exposing source systems or private results.

## Allowed content

- Stable governance and schemas.
- Reviewed knowledge notes, templates, skill manifests, field-family metadata, diagnostics, and negative-experience summaries.
- Manifest entries with exact path, SHA-256, byte size, provenance class, classification, and review state.

## Forbidden content

- Credentials, keys, tokens, cookies, account identifiers, network addresses, or connection strings.
- Raw forum or message databases, unreviewed copied material, raw provider payloads, or restricted documents.
- Databases, raw logs, environment files, backups, archives, submitted pools, complete PnL, or private results.
- Full application source code or deployment configuration.

## Change rules

- Human review is required before an entry becomes manifest-listed.
- Record provenance class without publishing private source identifiers.
- Update the schema before adding a new entry shape.
- Verify every manifest hash and size before commit.
- Use normal fast-forward history; never force-push over unverified remote history.
- This repository never becomes a runtime dependency or production fact source.
