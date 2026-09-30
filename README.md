<div align="center">

# Interview Project Bullets

### Turn real code into interview-ready engineering stories.

An evidence-first Codex skill for finding project improvements, learning from strong open-source PRs, and writing resume bullets you can defend in a technical interview.

<p>
  <a href="https://github.com/Sealessland/interview-project-bullets/actions/workflows/validate.yml"><img src="https://img.shields.io/github/actions/workflow/status/Sealessland/interview-project-bullets/validate.yml?label=validation" alt="Validation status"></a>
  <a href="https://github.com/Sealessland/interview-project-bullets/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Sealessland/interview-project-bullets" alt="MIT License"></a>
  <a href="https://github.com/Sealessland/interview-project-bullets"><img src="https://img.shields.io/github/stars/Sealessland/interview-project-bullets?style=flat" alt="GitHub stars"></a>
</p>

</div>

Most project descriptions fail in the same place: they sound polished until the interviewer asks, "How did you measure that?"

This skill starts from the repository. It traces the code, tests, configuration, and history; identifies a bounded improvement that matters for the target role; and turns verified work into a concise bullet and a deeper interview story.

## The workflow

```text
Target role
    |
    v
Project evidence -----> Role-relevant improvement
    |                              |
    |                              v
    +----------------------> Tests and measurements
                                   |
                                   v
                  Resume bullet + interview story
```

Open-source PRs are used as design references when they help answer a real project question. They provide vocabulary, invariants, test ideas, and trade-offs. They never count as proof that your project implemented the same behavior.

## What you get

| Output | What it answers |
| --- | --- |
| Project evidence map | What is actually implemented, partial, planned, or unknown? |
| Improvement shortlist | Which small changes create the strongest technical signal for this role? |
| PR research notes | Which upstream designs are relevant, and what can be adapted safely? |
| Resume bullets | How do I describe verified work with precise technical language? |
| Interview story | Can I explain the context, decision, implementation, result, and trade-off? |
| Follow-up questions | What will an interviewer ask after reading the bullet? |

## Example

**Request**

```text
Inspect this Go service and a backend job description. Find two reliability improvements
that are small enough to implement this week, then draft bullets only after validation.
```

**Evidence-backed result**

```text
Implemented bounded retries with exponential backoff for transient downstream errors,
and added fault-injection tests covering retry limits and terminal failures.
```

The result is deliberately precise. If a benchmark exists, the measured result can be added with its workload and baseline. If it does not, the skill produces a measurement plan instead of inventing a percentage.

## Why it stays credible

Every claim must trace to at least one of:

- inspected source code or configuration;
- a test, benchmark, or runtime observation;
- an explicit fact confirmed by the project owner.

The skill keeps completed work separate from proposals and marks unsupported claims. It does not invent users, traffic, production impact, ownership, or performance numbers.

## Install

Copy the skill directory into your Codex skills directory:

```bash
cp -a interview-project-bullets "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then ask Codex something like:

```text
Use $interview-project-bullets. Inspect this repository and the target role,
then propose three bounded improvements that can become defensible resume bullets.
```

The skill can also be discovered automatically when the request is about project-based resume bullets or interview preparation.

## Repository layout

```text
SKILL.md                                  Main workflow and boundaries
agents/openai.yaml                        UI metadata for Codex
references/pr-research.md                 Finding and validating reference PRs
references/bullet-and-interview-guide.md  Claim ledger, metrics, and interview stories
```

## Validate locally

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```

GitHub Actions runs a lightweight structure check on every push and pull request.

## Contributing

Improvements should make the guidance more useful without encouraging inflated claims. See [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

MIT. See [LICENSE](LICENSE).
