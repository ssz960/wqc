# Recommended Alpha Mining OS adoptions

1. Adopt `SE-004` and `SE-009`: canonical profile hash, immutable registry snapshot reservation, and pre-admission compatibility validation.
2. Adopt `SE-002` only as an internal state-machine pattern: parent/child work records, idempotent result materialization, explicit cancellation and timeout states.
3. Adopt `SE-003`: one shared scheduler owns budgets, retry/backoff and audit. Never encode public forum rate-limit numbers as policy.
4. Adopt `SE-005` and `SE-006`: datasets, fields, types, settings and compatible operators are versioned registry facts.
5. Adopt `SE-007` in a safe form: offline deterministic expression and profile validation before queueing. Do not use direct platform requests or credentials from community code.
6. Enforce `SE-008`: all real calls remain behind explicit human approval, API Gate, admission, scheduler, adapter and audit.
7. Keep `SE-010` advisory-only: forum RAG and Research Memory may rank and cite sources, but cannot become a runtime authority or decision gate.

Do not adopt quota, reward, Osmosis, Pyramid, or interface-specific values until the corresponding UNKNOWN claim has an approved current official source.
