# Paperpowers

Paperpowers is a research workflow system for coding agents.

It plays the role for `AI/CS empirical research` that `superpowers` plays for software development: it combines initial instructions, reusable skills, and a fixed workflow so agents behave like disciplined research partners instead of fast but sloppy assistants.

## What It Is

Paperpowers is designed for:

- problem framing
- literature grounding
- hypothesis shaping
- minimum-cost validation planning
- paper planning and drafting
- rebuttal preparation
- research claim verification

## What It Is Not

Paperpowers is not, in its initial scaffold:

- a full experiment orchestration platform
- a GPU scheduler
- a benchmark dashboard
- a general-purpose academic assistant for every discipline

The first scaffold focuses on research judgment, workflow discipline, and paper-oriented outputs.

## Long-Term Goal

Paperpowers is meant to grow beyond the current docs-and-skills scaffold into a fuller research workflow layer for coding agents.

The long-term target is:

- disciplined idea shaping and literature grounding
- minimum-cost validation before large compute commitments
- paper planning, drafting, and rebuttal support
- experiment execution, monitoring, and result analysis
- a tighter bridge between research judgment and empirical verification

The experiment layer is not implemented yet. That is intentional. The project is building the research judgment and paper-facing workflow first, then expanding toward experiment operations once the core workflow is stable.

## Core Workflow

The intended V1 workflow is:

`problem framing -> literature grounding -> hypothesis shaping -> quick validation plan -> direction decision -> paper plan -> section drafting -> evidence checking -> rebuttal prep`

## Initial Scaffold Contents

This repository currently ships:

- Codex integration files
- core philosophy and workflow docs
- nine foundational skills:
  - `using-paperpowers`
  - `research-brainstorming`
  - `literature-grounding`
  - `hypothesis-to-validation`
  - `paper-planning`
  - `paper-writing`
  - `rebuttal-prep`
  - `research-verification`
  - `writing-skills`

## Planned V1 Skills

- `using-paperpowers`
- `research-brainstorming`
- `literature-grounding`
- `hypothesis-to-validation`
- `paper-planning`
- `paper-writing`
- `rebuttal-prep`
- `research-verification`
- `writing-skills`

## Installation

For Codex, follow [`.codex/INSTALL.md`](.codex/INSTALL.md).

## Philosophy

Paperpowers optimizes for:

- evidence over vibes
- direction quality before implementation volume
- minimum-cost falsification before expensive experimentation
- narrative clarity before polished prose
- explicit claim-risk awareness

See [`docs/philosophy.md`](docs/philosophy.md) and [`docs/workflows/v1.md`](docs/workflows/v1.md).

## Repository Layout

```text
paperpowers/
├── .codex/
├── docs/
├── examples/
└── skills/
```

## Status

The repository is in its scaffold milestone. The current version documents the full V1 skill surface for `paperpowers`, covering idea shaping, literature grounding, minimum-cost validation planning, paper planning, section drafting, rebuttal preparation, research verification, and internal skill evolution.

## Contributing

If you want to contribute:

1. Start from an issue, discussion, or a clearly scoped proposal.
2. For substantial changes, add or update a design note under `docs/paperpowers/specs/` and a plan under `docs/paperpowers/plans/` before implementing.
3. Keep skills compact, triggerable, and workflow-oriented. A skill description should explain when to use it, not summarize the whole procedure.
4. Verify your changes before opening a PR. For skills, make sure the expected headings and trigger conditions are present. For docs, keep `README.md` aligned with the actual repo state.
5. Prefer focused PRs. A small skill, a doc improvement, or one workflow refinement is easier to review than a large mixed change.

Good first contributions include:

- improving examples
- refining trigger wording for existing skills
- adding missing workflow docs
- tightening verification rules
- proposing the future experiment layer in a concrete, staged way
