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

## KNOW-20260718-008 continuation patterns

- Research state is not a single pass/fail value. Candidate quality, gate result, throttling, pending work, timeout and missing observation need separate durable states so transient infrastructure does not discard a hypothesis.
- Capability metadata is profile-scoped and perishable. Only an authorized, versioned snapshot may enter candidate planning; community code that logs in or scrapes inventories is non-adoptable.
- A local correlation graph can compress a large research batch into families and representatives. It is a review-prioritization stage only, never a substitute for Self, Power Pool or Prod observations.
- Expression and source-file research inputs should normalize into one immutable candidate contract before admission. Direct REST, polling, submission and credential examples in the source material remain excluded.
- Semantic polarity and group-normalized study families are stored only as role placeholders. A human must validate the economic pairing, field type, operator availability and profile before a local research plan is created.

## Additional Manual Review Targets

- `TOPIC-41279111112855`: scoped CHN data-family and correlation retrospective; retain as a hypothesis, not a general rule.
- `TOPIC-35590188390551`: local Power Pool precheck implementation; verify official membership and freshness semantics before any design decision.
- `TOPIC-29064340617239`: capability discovery script includes credential/direct access material; retain only the snapshot-freshness lesson.
- `TOPIC-39922788056343`: promotion and tag narrative; do not infer tag-write behavior, eligibility or reward effects.

## KNOW-20260718-008 Deep Collection Patterns

- Candidate-quality discussion is most useful as an advisory review schema: hypothesis, data-family role, scope, simplicity concern and a separately named correlation hypothesis. It cannot turn a personal score, turnover band or Value-Factor story into admission policy.
- Python research needs a private semantic-state contract. History, state, missingness, numeric representation, data adjustment and resource cost are individually testable failure dimensions; none is proven by an operator-name translation.
- A private ledger can deduplicate research attempts and retain lifecycle states, but must remain downstream of hard admission and cannot call an adapter. Canonicalization, audit references and `UNKNOWN` recovery are more durable than a copied access script.
- Batch generation and AI assistance are safe only when they produce bounded, redacted CandidatePlans. Generation, static validation, admission, scheduling and reconciliation must stay separate.
- Numeric transforms and simplification are research mutations. They require a documented economic hypothesis and semantic comparison; no forum result establishes portability or a promotion benefit.
- Payment, VF, PPA and Osmosis narratives are time- or account-scoped. Treat them as manual-review alerts rather than reward, allocation, scoring or write logic.

## Later Deep Collection Patterns

- Session renewal, direct retry and historical result stores found in community code are non-adoptable. The safe abstraction is a single approved adapter with opaque error classes, idempotency keys, bounded retry and private audit pointers.
- Out-of-sample analysis is a private robustness-review stage. Scope, window and coverage must travel with every aggregate; a distributional review cannot be treated as an official check or a public result asset.
- Community reports of request counts, resets and local stop thresholds are counterevidence to hard-coded quota logic. A scheduler may reserve local budget but must label it non-authoritative and fail closed on uncertain external state.
- Multi-agent and Skill workflows are viable only as redacted, role-scoped advisory modules. Research memory is versioned context, not a platform authority or execution channel.

## KNOW-20260718-008 High-Signal Batch Patterns

- Local pairwise-return analysis can rank redundant research variants only after an authorized pullback. It must be profile-scoped, versioned and advisory; it cannot stand in for Self, Power Pool or Prod correlation.
- Field-family similarity requires a cache key covering scope, field identity, source version, coverage and observed-at time. It proposes a research branch, not a novelty verdict.
- Static parsing can create a private dependency manifest for CandidatePlan review. Registry validation and semantic-parity review remain independent gates.
- MCP and LLM helpers may turn sanitized metadata into research notes or draft descriptions. They do not receive private expressions, credentials, result data or platform authority.
- Account-write examples such as Osmosis allocation are retained only as non-adoptable risk evidence.

## KNOW-20260718-008 Current Deep-Collection Patterns

- Preserve a private research lineage distinct from a small, redacted decision summary. The summary can support human review, but it cannot reconstruct an expression, account result, raw payload, or execution intent.
- Make desired concurrency scheduler-owned and durable. Workers report leases, heartbeats, and opaque state transitions; they never invent platform capacity or independently retry a throttled call.
- Treat field shape, operator signature, and documentation mismatch as registry-validation problems. An automated repair is a new proposed candidate with a semantic-delta record, not a silent rewrite.
- Use role-only template taxonomies for research intake: primary role, secondary role, relationship hypothesis, optional conditioning role, and topology. Instantiate nothing until human semantic review and a scoped registry check pass.
- Direct command surfaces that expose auth, simulate, retrieve, mutate, or submit are non-adoptable. They are security-test inputs for local mocks, never a connector implementation.
- A private raw-artifact and progress-log layer can protect LLM context, provided that the LLM receives only a bounded redacted summary and has no adapter, budget, or write capability.

## Current Manual Review Targets

- `TOPIC-41706827651991`: direct command/control release; retain as a prohibited integration pattern.
- `TOPIC-41363885291031`: wrapper architecture; verify a sanitized summary contract without importing source execution logic.
- `TOPIC-35581087524503`: direct correlation utility; retain only as an ordering counterexample and credential risk.
- `TOPIC-40346082255255`: Osmosis narrative; obtain current official rule text before any interpretation.
- `TOPIC-40962462282007`: scoped check-repair narrative; reproduce only with a private one-mutation experiment and no formula publication.

## KNOW-20260718-008 Chinese Consultant Continuation Patterns

- A local correlation cache may remember private, authorized observations, but it is not a blacklist or an official correlation proxy. Its key must bind correlation kind, profile scope, observed-at time, freshness and provenance; cache hits remain advisory. `TOPIC-41377679573143` supplies a code-bearing cautionary example, not a reusable implementation.
- A research campaign can keep discovery, core definition, scaling, repair and review-packet work distinct. Stage records and bounded local budgets improve resume and learning behavior, but no stage creates an execution right. `TOPIC-41568235513623` is personal workflow evidence only.
- A regional check-repair story is an experiment seed, not a transformation catalogue. Preserve one intended mutation, scope and private before/after pointer; an ambiguous diagnosis remains `UNKNOWN`. `TOPIC-41162636720919` includes excluded code and result material.
- Two-source research can begin with economic roles, expected polarity and a confirmation-or-divergence hypothesis. Those tags improve research briefing but do not prove any correlation outcome or instantiate a formula. `TOPIC-41142979050775` is represented only by a role-only template intake record.
- Human, AI and deterministic components have different responsibilities: AI proposes bounded hypotheses, deterministic tooling validates approved metadata, and humans own objectives and decisions. `TOPIC-39304762113815` supports this advisory split; all reported thresholds, results and direct execution paths are excluded.
- Raw-to-summary projection remains a redaction and context-budget pattern, not a platform connector. `TOPIC-40530659645719` adds supporting evidence that verbose result payloads should remain in private artifacts and be disclosed to an LLM only through a bounded, redacted decision view.

## Additional Manual Review Targets

- `TOPIC-40962586503191`: promotion and Value Factor narrative; obtain current official criteria before any mechanism, dashboard, or goal model.
- `TOPIC-41377679573143`: test advisory-cache precision and freshness only with synthetic or approved private observations.
- `TOPIC-41162636720919`: require an official check definition and one-mutation local protocol before any scoped experiment.
- `TOPIC-41142979050775`: review the role-only hypothesis contract before field or operator instantiation.
