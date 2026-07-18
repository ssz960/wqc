# Research Knowledge Assets

This repository defines a public, sanitized contract for reviewed research knowledge and reusable research metadata.

The initial version contains governance, an empty manifest, and its validation schema only. It is not a source-code repository, runtime dependency, raw material archive, or production knowledge database.

Start with [AGENTS.md](AGENTS.md), [manifest.json](manifest.json), and [schema/research_knowledge_manifest.schema.json](schema/research_knowledge_manifest.schema.json).

Future entries must have clear provenance, completed human review, a content hash, and an explicit public-sanitized classification before publication.

Candidate claim sets may be stored outside `manifest.json` for human review. They must remain source-indexed, sanitized, and explicitly marked `PENDING_HUMAN_REVIEW`; only approved assets are manifest-listed.
