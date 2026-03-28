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

## Core Workflow

The intended V1 workflow is:

`problem framing -> literature grounding -> hypothesis shaping -> quick validation plan -> direction decision -> paper plan -> section drafting -> evidence checking -> rebuttal prep`

## Initial Scaffold Contents

This repository currently ships:

- Codex integration files
- core philosophy and workflow docs
- six foundational skills:
  - `using-paperpowers`
  - `research-brainstorming`
  - `literature-grounding`
  - `hypothesis-to-validation`
  - `paper-planning`
  - `research-verification`
- reserved directories for the remaining V1 skills

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

The repository is in its scaffold milestone. The current version already implements the front-half workflow for idea shaping, literature grounding, minimum-cost validation planning, and paper planning, while the remaining V1 skills are still being filled in.
