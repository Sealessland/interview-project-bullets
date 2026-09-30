# Interview Project Bullets

An agent skill for turning real software projects into truthful, role-targeted resume bullets and interview stories.

It inspects project evidence, identifies bounded improvements, uses analogous open-source pull requests as design references, and produces claims that can be defended from code, tests, benchmarks, or explicitly confirmed facts.

## What it does

- Builds a role and project evidence map.
- Finds project-shaped improvements with clear interview value.
- Verifies relevant open-source PRs before using them as references.
- Separates completed, partial, planned, and unknown work.
- Produces resume bullets, technical stories, metrics plans, and follow-up questions.
- Prevents invented scale, metrics, production impact, or ownership claims.

## Install

Copy the `interview-project-bullets` directory into `$CODEX_HOME/skills` or `~/.codex/skills`.

```bash
cp -a interview-project-bullets "${CODEX_HOME:-$HOME/.codex}/skills/"
```

The skill is automatically discoverable. It can also be invoked explicitly as `$interview-project-bullets` when supported by the host.

## Example requests

```text
Use this project and the attached backend job description to identify three improvements that would create strong, defensible resume bullets.
```

```text
Inspect this repository, find analogous open-source PRs for its reliability gaps, and draft bullets only for work that is implemented and tested.
```

## Evidence policy

The skill treats source code, configuration, tests, measurements, and explicit user facts as evidence. Open-source PRs guide design choices; they do not prove that the user's project contains or shipped the same behavior.

## Layout

```text
SKILL.md
references/
  bullet-and-interview-guide.md
  pr-research.md
```

## Validation

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```

## License

MIT. See [LICENSE](LICENSE).
