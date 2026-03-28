# Initial Paperpowers Scaffold Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build the first usable `paperpowers` repository scaffold for AI/CS empirical research, including repository docs, Codex integration files, and three foundational skills.

**Architecture:** Keep the initial release docs-first and workflow-first. The repository should establish the `paperpowers` identity, teach Codex how to activate the workflow, and provide three strong initial skills that constrain research behavior before adding broader skill coverage.

**Tech Stack:** Markdown, Git, Codex native skill discovery, shell verification

---

## File Structure

### Repository root

- Create: `README.md`
- Create: `LICENSE`
- Create: `.gitignore`

Responsibilities:

- `README.md` explains what `paperpowers` is, what it is not, how the workflow works, and what ships in the initial scaffold.
- `LICENSE` uses the MIT license so the repository is immediately publishable.
- `.gitignore` keeps common macOS and local noise out of version control.

### Codex integration

- Create: `.codex/AGENTS.md`
- Create: `.codex/INSTALL.md`

Responsibilities:

- `.codex/AGENTS.md` defines repo-local agent behavior and forces `paperpowers` workflow activation.
- `.codex/INSTALL.md` explains how to install the repository as a Codex skill bundle.

### Core docs

- Create: `docs/philosophy.md`
- Create: `docs/workflows/v1.md`
- Create: `examples/README.md`
- Create: `examples/idea-to-plan/README.md`
- Create: `examples/result-to-paper/README.md`
- Create: `examples/rebuttal/README.md`

Responsibilities:

- `docs/philosophy.md` states the research philosophy and evidence standards.
- `docs/workflows/v1.md` describes the intended V1 research workflow.
- `examples/*` give concrete entry points so the repo is immediately understandable.

### Initial skills

- Create: `skills/using-paperpowers/SKILL.md`
- Create: `skills/research-brainstorming/SKILL.md`
- Create: `skills/research-verification/SKILL.md`

Responsibilities:

- `using-paperpowers` is the session-entry rule system.
- `research-brainstorming` handles idea formation and direction shaping.
- `research-verification` prevents unsupported claims and weak conclusions.

### Future-skill scaffold

- Create: `skills/literature-grounding/.gitkeep`
- Create: `skills/hypothesis-to-validation/.gitkeep`
- Create: `skills/paper-planning/.gitkeep`
- Create: `skills/paper-writing/.gitkeep`
- Create: `skills/rebuttal-prep/.gitkeep`
- Create: `skills/writing-skills/.gitkeep`

Responsibilities:

- These directories reserve the intended V1 structure without pretending the remaining skills are implemented yet.

## Task 1: Repository Metadata and Identity

**Files:**
- Create: `README.md`
- Create: `LICENSE`
- Create: `.gitignore`

- [ ] **Step 1: Write `README.md`**

```markdown
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
- three foundational skills:
  - `using-paperpowers`
  - `research-brainstorming`
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

For Codex, follow [`/.codex/INSTALL.md`](.codex/INSTALL.md).

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

The repository is in its first scaffold milestone. The goal of this milestone is to produce a usable foundation rather than a complete research operating system.
```

- [ ] **Step 2: Verify `README.md` sections are present**

Run: `rg -n "^# Paperpowers|^## What It Is|^## What It Is Not|^## Core Workflow|^## Initial Scaffold Contents|^## Planned V1 Skills|^## Installation|^## Philosophy|^## Status" README.md`

Expected: matches for all nine headings

- [ ] **Step 3: Write `LICENSE`**

```text
MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

- [ ] **Step 4: Write `.gitignore`**

```gitignore
.DS_Store
Thumbs.db
*.swp
*.swo
.idea/
.vscode/
```

- [ ] **Step 5: Verify repository metadata files**

Run: `test -f README.md && test -f LICENSE && test -f .gitignore && rg -n "Paperpowers is a research workflow system" README.md && rg -n "^MIT License" LICENSE && rg -n "^\\.DS_Store$" .gitignore`

Expected: exit code 0 and one match from each `rg`

- [ ] **Step 6: Commit repository metadata**

```bash
git add README.md LICENSE .gitignore
git commit -m "docs: add paperpowers repository metadata"
```

## Task 2: Codex Integration and Research Workflow Docs

**Files:**
- Create: `.codex/AGENTS.md`
- Create: `.codex/INSTALL.md`
- Create: `docs/philosophy.md`
- Create: `docs/workflows/v1.md`
- Create: `examples/README.md`
- Create: `examples/idea-to-plan/README.md`
- Create: `examples/result-to-paper/README.md`
- Create: `examples/rebuttal/README.md`

- [ ] **Step 1: Write `.codex/AGENTS.md`**

```markdown
# Paperpowers Local Agent Rules

- Before answering any research-oriented request, check whether a `paperpowers` skill should be used.
- If there is any meaningful chance that the task is idea formation, research planning, paper writing, or rebuttal work, activate the relevant `paperpowers` workflow before acting.
- Do not jump from a vague research idea straight into implementation or paper drafting.
- For creative research work, use `research-brainstorming` before writing code, experiments, or prose.
- Do not claim novelty, empirical superiority, submission readiness, or rebuttal sufficiency without explicit evidence.
- If a claim is an inference rather than directly established fact, label it as an inference.
- Prefer minimum-cost falsification before expensive validation plans.
- Before drafting paper sections, ensure the current claims and evidence have been reconciled.
- User instructions override repo defaults.
```

- [ ] **Step 2: Write `.codex/INSTALL.md`**

```markdown
# Installing Paperpowers for Codex

Enable `paperpowers` skills in Codex through native skill discovery.

## Prerequisites

- Git

## Installation

1. Clone this repository into your Codex directory:

   ```bash
   git clone /Users/wangyunjeff/0_CODE/paperpowers ~/.codex/paperpowers
   ```

2. Create the skills symlink:

   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.codex/paperpowers/skills ~/.agents/skills/paperpowers
   ```

3. Restart Codex so it rediscovers skills.

## Verify

```bash
ls -la ~/.agents/skills/paperpowers
```

You should see a symlink pointing to the repository's `skills` directory.

If the repository is later published, replace the local source path with the hosted repository URL.
```

- [ ] **Step 3: Write `docs/philosophy.md`**

```markdown
# Paperpowers Philosophy

Paperpowers is built around one idea: research agents should behave like careful empirical collaborators, not like autocomplete systems with confidence.

## Core Principles

- Evidence before claims
- Falsify cheaply before scaling up
- Clarify the contribution before building machinery
- Separate observation from inference
- Turn results into arguments, not just artifacts

## Default Stance

If evidence is missing, say it is missing.

If a result is suggestive but weak, say it is suggestive but weak.

If a conclusion depends on interpretation, label it as interpretation.
```

- [ ] **Step 4: Write `docs/workflows/v1.md`**

```markdown
# Paperpowers V1 Workflow

## Main Flow

`problem framing -> literature grounding -> hypothesis shaping -> quick validation plan -> direction decision -> paper plan -> section drafting -> evidence checking -> rebuttal prep`

## Intent

- Front half: make the research direction defensible
- Middle: run the cheapest meaningful validation
- Back half: turn evidence into a clear paper and response strategy

## V1 Focus

The initial release prioritizes:

- idea to direction card
- direction to minimal validation
- results to paper structure
- reviews to rebuttal strategy
```

- [ ] **Step 5: Write `examples/README.md`**

```markdown
# Examples

This directory holds example entry points for common `paperpowers` workflows.
```

- [ ] **Step 6: Write `examples/idea-to-plan/README.md`**

```markdown
# Idea to Plan

Use this example pattern when starting from a vague direction and trying to end with a defensible direction card plus a minimal validation plan.
```

- [ ] **Step 7: Write `examples/result-to-paper/README.md`**

```markdown
# Result to Paper

Use this example pattern when experiments already exist and the agent needs to build a paper story, section outline, and claim inventory.
```

- [ ] **Step 8: Write `examples/rebuttal/README.md`**

```markdown
# Rebuttal

Use this example pattern when reviewer comments arrive and the agent needs to organize concessions, rebuttals, and follow-up evidence.
```

- [ ] **Step 9: Verify Codex integration and docs**

Run: `test -f .codex/AGENTS.md && test -f .codex/INSTALL.md && test -f docs/philosophy.md && test -f docs/workflows/v1.md && test -f examples/README.md && test -f examples/idea-to-plan/README.md && test -f examples/result-to-paper/README.md && test -f examples/rebuttal/README.md && rg -n "research-brainstorming" .codex/AGENTS.md && rg -n "Enable `paperpowers` skills" .codex/INSTALL.md && rg -n "^# Paperpowers Philosophy" docs/philosophy.md && rg -n "^# Paperpowers V1 Workflow" docs/workflows/v1.md`

Expected: exit code 0 and one match from each `rg`

- [ ] **Step 10: Commit Codex integration and docs**

```bash
git add .codex/AGENTS.md .codex/INSTALL.md docs/philosophy.md docs/workflows/v1.md examples/README.md examples/idea-to-plan/README.md examples/result-to-paper/README.md examples/rebuttal/README.md
git commit -m "docs: add codex integration and workflow docs"
```

## Task 3: Author `using-paperpowers`

**Files:**
- Create: `skills/using-paperpowers/SKILL.md`

- [ ] **Step 1: Write `skills/using-paperpowers/SKILL.md`**

```markdown
---
name: using-paperpowers
description: Use when starting any conversation that may involve AI/CS empirical research workflow decisions
---

<EXTREMELY-IMPORTANT>
If there is any meaningful chance a `paperpowers` skill applies, activate it before acting.
</EXTREMELY-IMPORTANT>

# Using Paperpowers

## Purpose

Paperpowers exists to make research workflow discipline automatic.

Before responding to a research request, determine whether the user is asking for:

- idea formation
- literature grounding
- hypothesis validation design
- paper planning or drafting
- rebuttal work
- research claim evaluation

If yes, route into the relevant `paperpowers` skill before acting.

## Core Rule

Do not jump directly to code, experiments, or polished prose when a research workflow should happen first.

## Skill Priority

1. `research-brainstorming` for vague ideas, pivots, and contribution shaping
2. `literature-grounding` for prior-work mapping and novelty tension
3. `hypothesis-to-validation` for minimum-cost falsification plans
4. `paper-planning` before drafting a paper from results
5. `paper-writing` after the paper plan is stable
6. `rebuttal-prep` for reviewer response strategy
7. `research-verification` before any strong claim about novelty, readiness, or empirical sufficiency

## Red Flags

These thoughts mean stop and activate the workflow:

- "I can just write the abstract first"
- "The idea is obvious enough"
- "We can worry about novelty later"
- "Let's plan the full benchmark suite immediately"
- "The numbers look good, so it is probably submission-ready"

## Default Behavior

- Ask clarifying questions before creative research work
- Prefer one decision at a time
- Separate evidence from inference
- Prefer cheap falsification before expensive expansion
- Tell the user when the current evidence bar is not met

## User Instructions

User instructions override repo defaults, but they do not remove the need for research discipline.
```

- [ ] **Step 2: Verify `using-paperpowers`**

Run: `test -f skills/using-paperpowers/SKILL.md && rg -n "^name: using-paperpowers$|^# Using Paperpowers$|^## Core Rule$|^## Skill Priority$|^## Red Flags$" skills/using-paperpowers/SKILL.md`

Expected: exit code 0 and matches for all five patterns

- [ ] **Step 3: Commit `using-paperpowers`**

```bash
git add skills/using-paperpowers/SKILL.md
git commit -m "skills: add using-paperpowers"
```

## Task 4: Author `research-brainstorming`

**Files:**
- Create: `skills/research-brainstorming/SKILL.md`

- [ ] **Step 1: Write `skills/research-brainstorming/SKILL.md`**

```markdown
---
name: research-brainstorming
description: Use before creative research work such as new ideas, pivots, contribution shaping, or evaluation design
---

# Research Brainstorming

Turn vague research intentions into defensible direction cards.

## Hard Gate

Do not jump from a vague research idea directly into experiments, code, or paper prose.

## Checklist

1. Explore available context
2. Ask clarifying questions one at a time
3. Identify the problem, stakes, and likely evidence bar
4. Propose 2-3 possible contribution shapes
5. Recommend one direction and explain why
6. Present a direction card
7. Write the direction spec to `docs/paperpowers/specs/YYYY-MM-DD-<topic>-design.md`
8. Ask the user to review the written spec before moving on
9. Transition to `hypothesis-to-validation` or `paper-planning` depending on project state

## Direction Card Contents

Every direction card should include:

- problem statement
- why it matters
- closest prior work
- failure boundary
- proposed angle
- expected contribution shape
- minimum validation plan
- major risks

## Interaction Rules

- Ask one question at a time
- Prefer narrowing over expanding scope
- Kill weak directions early
- Name uncertainty explicitly
- Avoid ornamental novelty

## Success Condition

The user leaves this stage with a direction that is clear enough to test and narrow enough to defend.
```

- [ ] **Step 2: Verify `research-brainstorming`**

Run: `test -f skills/research-brainstorming/SKILL.md && rg -n "^name: research-brainstorming$|^# Research Brainstorming$|^## Hard Gate$|^## Checklist$|^## Direction Card Contents$|^## Success Condition$" skills/research-brainstorming/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `research-brainstorming`**

```bash
git add skills/research-brainstorming/SKILL.md
git commit -m "skills: add research-brainstorming"
```

## Task 5: Author `research-verification` and Reserve Future Skill Directories

**Files:**
- Create: `skills/research-verification/SKILL.md`
- Create: `skills/literature-grounding/.gitkeep`
- Create: `skills/hypothesis-to-validation/.gitkeep`
- Create: `skills/paper-planning/.gitkeep`
- Create: `skills/paper-writing/.gitkeep`
- Create: `skills/rebuttal-prep/.gitkeep`
- Create: `skills/writing-skills/.gitkeep`

- [ ] **Step 1: Write `skills/research-verification/SKILL.md`**

```markdown
---
name: research-verification
description: Use before claiming novelty, empirical superiority, readiness, or sufficiency of evidence
---

# Research Verification

## Iron Law

No strong research claim without explicit evidence.

## Gate Function

Before making any claim, answer:

1. What exact claim is being made?
2. What evidence directly supports it?
3. What part is still inference?
4. What uncertainty remains?
5. Does the wording match the evidence bar?

If any answer is weak or missing, weaken the claim or state the gap explicitly.

## Claim Types That Require Verification

- novelty
- empirical improvement
- causal interpretation
- generalization
- submission readiness
- rebuttal sufficiency

## Required Output Style

- State facts as facts
- State inferences as inferences
- State missing evidence as missing evidence
- Never promote a promising signal into a settled conclusion

## Failure Modes

- "Looks novel"
- "Probably enough for a paper"
- "The gain is clear" without baselines or variance
- "This addresses the review" without checking the reviewer's actual concern
```

- [ ] **Step 2: Create future-skill scaffold directories**

```bash
mkdir -p skills/literature-grounding \
         skills/hypothesis-to-validation \
         skills/paper-planning \
         skills/paper-writing \
         skills/rebuttal-prep \
         skills/writing-skills
touch skills/literature-grounding/.gitkeep \
      skills/hypothesis-to-validation/.gitkeep \
      skills/paper-planning/.gitkeep \
      skills/paper-writing/.gitkeep \
      skills/rebuttal-prep/.gitkeep \
      skills/writing-skills/.gitkeep
```

- [ ] **Step 3: Verify `research-verification` and scaffold directories**

Run: `test -f skills/research-verification/SKILL.md && test -f skills/literature-grounding/.gitkeep && test -f skills/hypothesis-to-validation/.gitkeep && test -f skills/paper-planning/.gitkeep && test -f skills/paper-writing/.gitkeep && test -f skills/rebuttal-prep/.gitkeep && test -f skills/writing-skills/.gitkeep && rg -n "^name: research-verification$|^# Research Verification$|^## Iron Law$|^## Gate Function$|^## Claim Types That Require Verification$|^## Failure Modes$" skills/research-verification/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 4: Commit verification skill and scaffold directories**

```bash
git add skills/research-verification/SKILL.md skills/literature-grounding/.gitkeep skills/hypothesis-to-validation/.gitkeep skills/paper-planning/.gitkeep skills/paper-writing/.gitkeep skills/rebuttal-prep/.gitkeep skills/writing-skills/.gitkeep
git commit -m "skills: add research verification and v1 scaffold"
```

## Self-Review

### Spec coverage

- Product identity and scope: covered by Task 1 and Task 2
- Codex workflow glue: covered by Task 2 and Task 3
- Initial authored skill subset: covered by Task 3, Task 4, and Task 5
- Repository structure: covered by Task 1, Task 2, and Task 5
- V1 versus scaffold distinction: represented in `README.md` and reserved future-skill directories

No spec gaps remain for the initial scaffold milestone.

### Placeholder scan

Search after writing the plan:

Run:

```bash
python - <<'PY'
from pathlib import Path

text = Path("docs/paperpowers/plans/2026-03-28-initial-scaffold.md").read_text()
patterns = [
    "TB" + "D",
    "TO" + "DO",
    "FIX" + "ME",
    "implement" + " later",
    "fill" + " in details",
    "appropriate" + " error handling",
    "Similar" + " to Task",
]
matches = [p for p in patterns if p in text]
print(matches)
raise SystemExit(1 if matches else 0)
PY
```

Expected: no matches

### Type consistency

- Skill names used in docs match directory names
- Repo paths in the plan match the spec paths
- The scaffold milestone is explicitly separated from the full V1 product definition
