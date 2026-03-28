**English** | [简体中文](README_CN.md)

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

### Personal Design Philosophy

This project also follows a more personal design philosophy about research ideation and literature work.

First, brainstorming is not only about collecting papers. Literature review is necessary, but the style of thinking matters just as much. One of the references behind this direction is the ideation track in [Orchestra Research's AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs/tree/main/21-research-ideation), especially the split between `brainstorming-research-ideas` and `creative-thinking-for-research`.

Second, brainstorming should eventually be split by scenario instead of treated as a single generic mode. Different situations need different balances between divergence, convergence, feasibility, and literature depth. Examples include:

- **Paradigm-shift exploration in a crowded field**: when a research area has already entered the "last 1-2% improvement" stage and incremental gains are no longer exciting, the system should bias toward more divergent thinking and possible new paradigms. This mode is closer to `creative-thinking-for-research`.
- **Convergent, actionable idea formation**: when the goal is a realistic, defensible, and implementable plan, the system should bias toward narrowing, decision-making, and practical research design. This mode is closer to `brainstorming-research-ideas`.
- **Safe idea generation for students**: sometimes the goal is not the boldest idea, but a set of solid, teachable, low-risk directions that students can actually execute well.
- **Feasibility discussion mode**: sometimes the user does not primarily need a final idea at all, but rather material for a group meeting, proposal discussion, or a conversation with an advisor about whether a plan is viable.

Third, different scenarios should demand different amounts of brainstorming and literature grounding. Some situations require wide exploration before committing. Others require fast convergence with only the minimum necessary literature map. The workflow should adapt instead of forcing the same ideation depth every time.

Fourth, personalization should matter. The system should ideally know the researcher's own history and preferences before doing brainstorming or literature search. A future version should be able to read from a local folder that ranks:

- papers the researcher has published
- papers the researcher has studied carefully
- papers the researcher is interested in

That personal library should influence search and grounding priority. In addition, venue quality should matter: top conference papers should usually receive higher search weight than unreviewed arXiv papers unless the task explicitly calls for frontier preprints.

This philosophy is a design target for future `paperpowers` evolution. It is not fully implemented in the current scaffold, but it defines the direction the project is intended to grow toward.

### Experiment-Layer Design Philosophy

For the future experiment layer, two important references are [Orchestra Research's `autoresearch` skill](https://github.com/Orchestra-Research/AI-Research-SKILLs/tree/main/0-autoresearch-skill) and [Karpathy's `autoresearch`](https://github.com/karpathy/autoresearch). They suggest a philosophy that is worth making explicit here.

First, experiment execution should not be treated as a bag of disconnected runs. It should be an organized research loop with memory, direction, and judgment. A useful design is to separate:

- an **inner loop** for fast, bounded experiments with a clear metric or hypothesis test
- an **outer loop** for synthesis, reflection, pattern-finding, and direction changes

Second, the experiment layer should optimize for **cheap, comparable iteration**. Karpathy's project is especially strong on this point: keep the setup small, keep the optimization target clear, keep the editable surface narrow, and use a fixed budget whenever possible so runs can be compared fairly. The future `paperpowers` experiment layer should inherit that spirit even if the exact execution environment becomes more general.

Third, experiment orchestration and domain execution should be separated. The orchestration layer should decide what hypothesis to test, what to measure, when to pivot, and when to conclude. Domain-specific skills or tools should handle the actual implementation details of training, evaluation, plotting, or infrastructure.

Fourth, structured project memory matters. Experiment logs alone are not enough. A good research loop needs explicit state, trajectory tracking, synthesized findings, and records of what was learned, not just what was run. This is important both for autonomous continuation and for human interpretability.

Fifth, negative results should be treated as real research progress. The experiment layer should preserve what was ruled out, distinguish confirmatory from exploratory findings, and make it easy to avoid repeating failed directions.

Sixth, simplicity should remain a first-class value. If a change slightly improves a metric but adds disproportionate complexity, that tradeoff should be visible. The future system should not only chase improvement; it should reason about whether the gain is actually worth the added machinery.

Seventh, autonomy should be paired with periodic communication. A strong experiment layer should be able to keep running without constant user intervention, while still producing progress reports, trajectories, and interpretable updates so the human can step in when needed.

In short, the experiment layer in `paperpowers` should eventually become a bridge between research judgment and empirical execution: not just "run more experiments", but "run the right experiments, under controlled conditions, with memory, synthesis, and a path to paper-level understanding." This is still a design direction, not a completed feature in the current scaffold.

### Possible Future Experiment Skills

The philosophy above also suggests a set of possible future skills. These are not implemented yet, and they are not a frozen roadmap, but they make the intended experiment layer more concrete:

- `experiment-orchestration`
  Decide which hypothesis to test next, what evidence would be decisive, and whether the next step should be a new run, an ablation, a rollback, or a pivot.
- `experiment-inner-loop`
  Run short, bounded, comparable experiment cycles under a fixed budget, with explicit metrics and stop conditions.
- `experiment-monitoring`
  Watch long-running jobs, surface failures early, summarize checkpoints, and decide when a run should continue or be terminated.
- `experiment-memory`
  Maintain structured state for hypotheses, tried variants, confirmed findings, rejected directions, and experiment trajectories.
- `results-synthesis`
  Turn a collection of runs into patterns, failure analyses, negative-result summaries, and next-step recommendations.
- `benchmark-discipline`
  Enforce fair comparisons, stable evaluation settings, and explicit reporting of what changed between runs.
- `claim-to-evidence`
  Connect experiment results back to the paper story, updating the claim-evidence matrix instead of treating experiments and writing as separate worlds.

Taken together, these possible skills point toward an experiment layer that is not just about execution, but about disciplined iteration, memory, comparability, and scientific interpretation.

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
