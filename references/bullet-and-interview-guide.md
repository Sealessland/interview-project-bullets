# Resume bullets and interview stories

## Claim ledger

Before drafting, link each phrase to evidence:

| Claim | Evidence | Status | Safe wording |
|---|---|---|---|
| behavior or component | source path, test, config, or confirmed fact | complete / partial / planned | precise verb and scope |
| impact or metric | benchmark, logs, before/after, or confirmed fact | measured / unmeasured | number with conditions, or qualitative outcome |
| ownership | commit/history or user confirmation | confirmed / unclear | built / implemented / contributed / explored |

Remove or qualify any claim without evidence. “Designed” does not imply shipped; “production” requires explicit confirmation. Distinguish personal work from inherited code and team outcomes.

## Bullet shape

Use: **strong verb + system/change + technical mechanism + verified result or validation**. Keep the problem and trade-off available for discussion, but avoid packing every implementation detail into one sentence.

Good evidence-based pattern:

```text
Implemented bounded retries with exponential backoff for transient downstream errors, and added fault-injection tests to verify retry limits and terminal failure behavior.
```

This describes implementation and validation without inventing an impact number. If a measured improvement exists, add the metric with workload, baseline, and environment. Avoid unsupported phrases such as “highly scalable,” “massive traffic,” “production-grade,” or “improved performance by X%.”

## Metrics

Choose metrics that match the change: p50/p95/p99 latency, throughput, error rate, recovery time, resource use, query count, build time, test flakiness, or coverage of a failure mode. Measure a baseline and changed version under the same representative workload. Record hardware/runtime, dataset, concurrency, warm-up, sample count, and command. Do not compare unlike runs or infer production impact from a microbenchmark.

When measurement is not yet possible, output a “measure next” item, not a fabricated result. Examples:

- Compare p95 latency and allocation rate before/after using the same workload.
- Inject a downstream timeout and verify retry count, total deadline, and final error.
- Restart a worker during processing and verify idempotency and recovery behavior.

## Interview story

Prepare a 60-90 second explanation:

1. **Context:** what the project did and where the issue appeared.
2. **Constraint:** why a simpler solution was insufficient.
3. **Decision:** chosen design and rejected alternative.
4. **Implementation:** the data/control path and key invariants.
5. **Validation:** tests and measured result, with limits.
6. **Trade-off:** complexity or failure mode introduced.
7. **Next step:** the most valuable remaining improvement.

Generate follow-ups from actual code: concurrency and state ownership, error paths, API boundaries, persistence semantics, compatibility, resource limits, test gaps, and operational failure handling. Ask questions the candidate can answer by tracing their own implementation. Provide answer outlines grounded in code; do not write a memorized script that overstates expertise.
