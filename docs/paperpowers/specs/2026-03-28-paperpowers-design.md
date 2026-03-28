# Paperpowers Design

Date: 2026-03-28
Status: Approved in conversation, written for review before planning

## Summary

`paperpowers` is a research workflow system for coding agents, modeled after the role `superpowers` plays for software development.

Its target domain is `AI/CS empirical research`.

It combines:

- initial instructions that enforce research-first behavior
- composable skills for research work
- a fixed workflow that prevents agents from skipping critical thinking, evidence gathering, and claim checking

The first release is intentionally not a full research infrastructure stack. It prioritizes research judgment and research communication over heavyweight experiment orchestration.

## Problem

Current coding agents are often strong at execution but weak at disciplined research process. In AI/CS empirical work, this creates recurring failure modes:

- jumping from a vague idea directly into implementation
- citing papers without building a field map or failure boundary
- over-designing experiments before testing whether the core hypothesis is even viable
- writing paper text before claims and evidence are aligned
- producing rebuttals that are reactive rather than strategically organized
- making research-quality claims without proof

`paperpowers` exists to make the correct workflow the default workflow.

## Product Definition

`paperpowers` is "Superpowers for AI/CS empirical research."

Like `superpowers`, it is not just a folder of prompts. It is a complete workflow system that shapes agent behavior from the start of the session.

The system has three layers:

1. `Initial instructions`
   These tell the agent how to behave before any task starts. The main requirement is that the agent must not jump straight to implementation, paper drafting, or conclusion-making when a research workflow should happen first.

2. `Skills`
   These are reusable guides for recurring research tasks such as idea formation, literature grounding, hypothesis validation, paper planning, and rebuttal preparation.

3. `Workflow glue`
   This defines the default order of operations and transition gates between stages.

## Target User

The primary user is a researcher doing AI/CS empirical work who wants an agent that behaves more like a careful research partner than a fast but sloppy assistant.

Typical scenarios:

- exploring a new research direction
- checking whether a direction is likely to be novel and defensible
- designing a minimum-cost validation before a large experimental commitment
- turning a pile of results into a paper story
- preparing a rebuttal strategy from reviewer comments

## Design Principles

`paperpowers` should optimize for:

- research discipline over speed theater
- evidence over vibe-based claims
- direction quality before implementation volume
- minimum-cost falsification before expensive experimentation
- paper-quality narrative structure before polished prose
- explicit non-goals and decision gates

## V1 Scope

The first version must be strong at four outcomes.

### 1. Idea to Direction Card

Convert a vague idea into a clear direction card with:

- problem statement
- why the problem matters
- closest prior work
- failure boundary
- proposed angle
- expected contribution shape
- minimum validation plan

### 2. Direction Card to Minimal Validation

Turn a direction into the smallest credible validation plan that can quickly reject weak hypotheses.

This stage should favor sanity checks, ablations, toy settings, and cheap pilots over full benchmark campaigns.

### 3. Results to Paper Structure

Convert an experiment state into:

- narrative spine
- section outline
- claim inventory
- evidence gaps
- required figures and tables

### 4. Review to Rebuttal Strategy

Convert reviewer comments into:

- issue classification
- which points to concede
- which points to rebut
- what new evidence is needed
- a structured response plan

## Explicit Non-Goals for V1

The first release does not try to solve everything in research engineering.

Out of scope:

- full experiment scheduling and GPU orchestration
- large-scale hyperparameter search management
- dashboard-heavy project tracking
- fully automated submission packaging
- general-purpose support for all academic disciplines

These may be added later, but they are not part of the initial product definition.

## Core Workflow

The default V1 workflow is:

`problem framing -> literature grounding -> hypothesis shaping -> quick validation plan -> direction decision -> paper plan -> section drafting -> evidence checking -> rebuttal prep`

Important intent behind this workflow:

- the front half is about making the research direction credible
- the back half is about turning evidence into a paper and defending it
- the middle validation step is intentionally lightweight

The workflow should stop agents from taking shortcuts such as:

- skipping literature grounding
- overclaiming novelty before checking closest prior work
- proposing a full experiment matrix before a cheap hypothesis test
- writing paper sections before claims and evidence are reconciled

## Skill System for V1

The initial skill set should be small and opinionated.

### Required skills

- `using-paperpowers`
  Session-entry skill. Teaches the agent to check whether a research workflow should be activated before doing anything else.

- `research-brainstorming`
  Used before any creative research work. Helps refine a problem, contribution shape, constraints, success criteria, and likely evaluation logic.

- `literature-grounding`
  Builds a field map, identifies closest work, and clarifies novelty tension and failure boundaries.

- `hypothesis-to-validation`
  Converts a research direction into minimum-cost experiments that can reject weak ideas quickly.

- `paper-planning`
  Converts results and claims into a paper plan with narrative logic and evidence mapping.

- `paper-writing`
  Produces section drafts only after the paper plan is stable.

- `rebuttal-prep`
  Produces a response strategy and response draft structure from review feedback.

- `research-verification`
  Prevents unsupported claims about novelty, effect size, readiness, or sufficiency of evidence.

- `writing-skills`
  Internal meta-skill for evolving `paperpowers` itself.

### Initial scaffold milestone

The first repository scaffold may ship with these three authored first:

- `using-paperpowers`
- `research-brainstorming`
- `research-verification`

This is a delivery-order decision, not a change to the V1 product definition.

The remaining skills should be added in the next implementation wave so that the full V1 workflow is covered.

## Repository Structure

The repository should live at:

`/Users/wangyunjeff/0_CODE/paperpowers`

Initial structure:

```text
paperpowers/
├── README.md
├── LICENSE
├── .codex/
│   ├── AGENTS.md
│   └── INSTALL.md
├── docs/
│   ├── philosophy.md
│   ├── workflows/
│   ├── examples/
│   └── paperpowers/
│       ├── specs/
│       └── plans/
├── skills/
│   ├── using-paperpowers/
│   ├── research-brainstorming/
│   ├── literature-grounding/
│   ├── hypothesis-to-validation/
│   ├── paper-planning/
│   ├── paper-writing/
│   ├── rebuttal-prep/
│   ├── research-verification/
│   └── writing-skills/
└── examples/
    ├── idea-to-plan/
    ├── result-to-paper/
    └── rebuttal/
```

## Why This Shape

This structure keeps the repository centered on reusable workflow logic rather than scripts or infrastructure.

It also matches the way users will reason about the system:

- docs explain the philosophy and workflow
- skills encode the operating behavior
- examples show what good outputs look like

## Evidence and Verification Rules

V1 should treat research verification as a first-class system feature, not a nice-to-have.

At minimum, the system should guard against unsupported claims in these categories:

- novelty
- empirical improvement
- causal interpretation
- submission readiness
- rebuttal sufficiency

The default stance should be:

- if evidence is missing, say it is missing
- if a claim is an inference, label it as an inference
- if a result is promising but weak, say so explicitly

## Interaction Model

The system should behave similarly to `superpowers` in spirit:

- ask clarifying questions before doing creative work
- propose alternatives before settling
- write down the design before implementation
- create explicit plans before multi-step execution
- verify before claiming success

The domain-specific adaptation is that "implementation" is not the only terminal activity. In `paperpowers`, the terminal activity may instead be:

- a direction card
- a validation plan
- a paper outline
- a section draft
- a rebuttal strategy

## Future Expansion

The most likely V2 directions are:

- experiment monitoring and lightweight orchestration
- result analysis helpers
- figure and table planning support
- integrated novelty checking and claim-risk assessment
- stronger support for multi-agent research loops

These should only be added if they strengthen the core research workflow rather than turning the project into a general lab platform.

## Acceptance Criteria for V1

V1 is successful if a user can:

1. install `paperpowers`
2. trigger a research workflow automatically in a new agent session
3. get a disciplined idea-to-direction interaction
4. get a minimum validation plan instead of a bloated experiment wishlist
5. turn result bundles into a paper plan
6. turn reviewer comments into a rebuttal strategy

## Open Decision

No blocking product questions remain for the V1 scaffold.

The only staged decision is implementation order:

1. repository scaffold and docs
2. session-entry and research-discipline skills
3. literature and validation skills
4. paper and rebuttal skills

That order is recommended because it yields a usable skeleton quickly while keeping the strongest workflow constraints in place from the start.
