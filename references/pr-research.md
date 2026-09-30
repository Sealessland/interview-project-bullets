# Open-source PR research for project building

Use this only when external implementation evidence can resolve a real project gap. The goal is to find a design worth adapting, not to collect impressive-looking links.

## Search from a local gap

Build queries from three parts: capability, failure mode, and evidence. Example: `bounded retry + duplicate request + merged regression test`. Search in this order:

1. The exact dependency or framework already used.
2. Projects with a similar architecture or data-flow boundary.
3. Projects solving the same workload in another language.
4. Foundational libraries or standards when the concern is protocol-level.

Use forge filters for merged PRs/MRs, labels, changed paths, and language as available. Record query, date, repository, PR URL, and final commit SHA. Search snippets are discovery hints only.

## Verify before borrowing

Inspect the final diff, tests, linked issue, review discussion, CI, release note, and follow-up changes. Confirm what behavior changed, under which version/runtime assumptions, and whether the change was reverted or constrained later. Prefer work with a reproducible test, benchmark, incident report, or migration explanation. If the evidence is weak, mark it as a study reference and reduce confidence.

## Adaptation record

For each useful reference capture:

```text
Local gap and evidence:
Reference PR and final SHA:
Upstream invariant/design lesson:
Local module and compatible approach:
What is intentionally not copied:
Validation to add:
Risk and confidence:
```

Compare dependency versions, public API, runtime, data model, license, and operational assumptions. Borrow the smallest idea that solves the evidenced local problem. Include the PR URL in learning notes, but do not imply the user's implementation came from or was accepted upstream unless that is true.

## Candidate selection

Favor candidates that create an explainable engineering story: clear problem, nontrivial but bounded decision, testable result, and meaningful trade-off. A small correctness fix with a strong regression test can be more valuable than a large subsystem. Reject candidates that add complexity without strengthening a real role-relevant capability.
