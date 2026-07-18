# External System Patterns: Correlation and Research Orchestration

All items are sanitized candidates for human review. They are not production instructions and do not authorize platform access.

## Recommended low-cost correlation funnel

1. Offline/local candidate hygiene and profile validation.
2. Optional Self observation when it is already available through an authorized read path.
3. Optional PP observation as a *prioritization signal only*.
4. Authorized Prod request through one shared scheduler only for candidates selected by a human-approved, locally calibrated policy.
5. Store an immutable observation record: correlation kind, profile hash, observed-at, cache freshness, result state, and source provenance.

Every threshold is **PENDING LOCAL VALIDATION**. The funnel cannot reject, submit, or mutate an Alpha. `Self < PP < Prod` has one explicitly unsupported forum sample and counterexamples/context that prevent any hard-rule interpretation.

## Reusable architecture

- `CorrelationRequest`: idempotency key, kind, profile version, state, attempt count, next eligible time, and audit reference.
- `CorrelationObservation`: result state, observed-at, freshness class, source version, and opaque error class; never store an Alpha expression or production payload in public assets.
- Shared scheduler: one bounded queue and one budget owner; no caller-owned retry loops.
- Parent/child model: parent lifecycle and every child lifecycle are stored separately. Parent completion never implies every child has a usable result.
- Durable materialization: atomically create-or-return a result record. Timeout and missing data are `UNKNOWN`, not successful or failed research conclusions.
- Recovery: classify throttled, unavailable, malformed, timeout, cancelled, and unknown states. Resume only from a committed state transition.

## Non-adoption boundary

Forum and public GitHub sources included direct authentication, endpoint, polling, execution, or result payload logic. None is copied, imported, run, or adopted. The retained patterns are only state machines, queue ownership, caching, retry classification, durable result records, and redaction boundaries.

## Manual Review Targets

- `TOPIC-33601626915351`: direct Prod retrieval code; preserve page locator, classify code as non-adoptable.
- `TOPIC-32223192365207`: PP/Prod-looking failure semantics; require current authoritative error mapping.
- `TOPIC-33089748320791`: explicitly unsupported Self/PP/Prod ordering hypothesis.
- `TOPIC-32970978828951`: direct collection/storage code; retain only safe architectural abstractions.
- `TOPIC-39118594803095`: experiment evidence and quality tradeoffs.
