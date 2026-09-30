---
name: interview-project-bullets
description: Turn an existing or planned software project into truthful, role-targeted resume bullets and interview stories, using code evidence and carefully selected open-source PRs to guide implementation.
metadata:
  short-description: Build evidence-backed project bullets for interviews
---

# Interview Project Bullets

Use this skill when the user is building, improving, or presenting a software project for recruiting, interviews, internships, or technical assessment. It helps choose demonstrable project work, learn from analogous open-source PRs, implement a bounded improvement when asked, and produce truthful resume bullets plus interview preparation.

## Core rule

Every claim must be supported by one of: (1) inspected code/configuration, (2) a test, benchmark, or runtime observation, or (3) an explicit user-provided fact. Keep proposals and unimplemented work separate from completed achievements. Never invent users, scale, impact, ownership, metrics, production use, or upstream contribution.

## Workflow

1. **Set the target.** Extract role, seniority, target company/domain when provided, required skills, resume language, and constraints. If the job description is available, rank its requirements by relevance. Ask only for information that blocks useful work; otherwise state assumptions.
2. **Inspect the project.** Read repository manifests, architecture, key flows, tests/CI, deployment, observability, recent history, and docs. Build a compact evidence map with file paths/symbols and classify each point as implemented, partially implemented, planned, or unknown. Do not infer depth from dependency names.
3. **Find project-shaped opportunities.** Identify the smallest gaps that can demonstrate high-value role skills through an end-to-end behavior. Prefer work that adds a meaningful capability or quality property, crosses an important boundary, and can be explained from problem through trade-off and validation. Avoid feature accumulation, gratuitous infrastructure, and unrelated complexity.
4. **Use open source as a design source.** When useful, search analogous projects for merged/reviewed PRs addressing the same capability or failure mode. Read the diff, tests, issue/review context, release status, and follow-ups. Extract the invariant, design choice, test strategy, or operational lesson; adapt it to the local architecture and versions. A reference PR is evidence for a design, never evidence that the user's project has implemented it. For search and verification detail, read [references/pr-research.md](references/pr-research.md).
5. **Choose a bounded implementation.** Rank candidate work by role relevance, project fit, demonstrable depth, validation strength, effort, and risk. State the expected evidence before coding: behavior, tests, measurement, and interview concepts. If the user asks to build it, implement and run the relevant checks; otherwise present a concrete plan. Do not add a change solely to improve resume wording.
6. **Verify claims.** After implementation, inspect the diff and run focused tests or benchmarks. Record exact commands and results. Metrics must be measured under stated conditions with a comparable baseline. If there is no baseline or representative workload, report that limitation and offer a measurement plan rather than a number.
7. **Write and prepare.** Produce concise bullets tailored to the target role, plus a technical story and likely follow-up questions. Read [references/bullet-and-interview-guide.md](references/bullet-and-interview-guide.md) for claim strength, bullet construction, and probing. Keep each sentence explainable by the candidate.

## Output contract

For project selection or improvement, return:

- role fit and the strongest project evidence found;
- top 3-5 bounded improvements, with expected skill signal, effort, evidence to collect, and risks;
- relevant open-source PR references only when they improve the decision;
- completed work separately from proposed work;
- resume bullet variants only for verified work, with unsupported claims flagged;
- interview story covering context, decision, implementation, validation, trade-off, and next improvement;
- likely follow-up questions grounded in actual code, with answer points rather than memorized scripts.

For bullet-only requests, still inspect the project or supplied evidence first. If no project evidence is available, ask for a repository or facts and provide only clearly labeled templates, never fabricated accomplishments.

## Boundaries

- Do not copy a PR wholesale without checking license, compatibility, and local design.
- Do not claim a benchmark, test, deployment, production impact, or contribution that was not observed or explicitly confirmed.
- Do not turn the response into generic career advice; keep recommendations tied to the target role and project evidence.
- Treat external browsing and forge access as research. Do not create forks, issues, comments, or submissions unless explicitly requested.

## References

- Read [references/pr-research.md](references/pr-research.md) for finding and validating open-source PRs as implementation references.
- Read [references/bullet-and-interview-guide.md](references/bullet-and-interview-guide.md) when producing resume language or interview preparation.
