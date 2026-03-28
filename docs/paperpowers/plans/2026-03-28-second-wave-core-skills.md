# Second-Wave Core Skills Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add the next three core `paperpowers` skills so the repository can cover literature grounding, minimum-cost validation planning, and paper planning.

**Architecture:** Extend the existing scaffold by filling the three reserved skill directories with compact but opinionated workflow documents. Keep the style aligned with the current `paperpowers` skills: hard gates, explicit checklists, and concrete success conditions. Update top-level docs so the repository accurately reflects the new capability set.

**Tech Stack:** Markdown, Git, shell verification

---

## File Structure

### Capability docs

- Modify: `README.md`

Responsibilities:

- `README.md` must accurately describe which skills are already implemented versus which are still planned.

### New skills

- Create: `skills/literature-grounding/SKILL.md`
- Create: `skills/hypothesis-to-validation/SKILL.md`
- Create: `skills/paper-planning/SKILL.md`
- Delete: `skills/literature-grounding/.gitkeep`
- Delete: `skills/hypothesis-to-validation/.gitkeep`
- Delete: `skills/paper-planning/.gitkeep`

Responsibilities:

- `literature-grounding` must stop vague novelty claims and produce a usable field map.
- `hypothesis-to-validation` must turn a direction into cheap falsification tests, not bloated experiment wishlists.
- `paper-planning` must force claim-evidence reconciliation before paper drafting.

## Task 1: Update Repository Capability Summary

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Update `README.md` initial scaffold section**

Replace the current "three foundational skills" block with:

```markdown
- six foundational skills:
  - `using-paperpowers`
  - `research-brainstorming`
  - `literature-grounding`
  - `hypothesis-to-validation`
  - `paper-planning`
  - `research-verification`
- reserved directories for the remaining V1 skills
```

- [ ] **Step 2: Update `README.md` status sentence**

Ensure the status section still says the repository is in its scaffold milestone, but now makes clear that the front-half workflow is implemented.

Use this paragraph:

```markdown
The repository is in its scaffold milestone. The current version already implements the front-half workflow for idea shaping, literature grounding, minimum-cost validation planning, and paper planning, while the remaining V1 skills are still being filled in.
```

- [ ] **Step 3: Verify `README.md` capability summary**

Run: `rg -n "six foundational skills|literature-grounding|hypothesis-to-validation|paper-planning|front-half workflow is implemented" README.md`

Expected: matches for all capability additions and the updated status wording

- [ ] **Step 4: Commit README capability update**

```bash
git add README.md
git commit -m "docs: update readme for second-wave skills"
```

## Task 2: Author `literature-grounding`

**Files:**
- Create: `skills/literature-grounding/SKILL.md`
- Delete: `skills/literature-grounding/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/literature-grounding/SKILL.md`**

Write this content:

```markdown
---
name: literature-grounding
description: Use when a research direction needs prior-work mapping, novelty-risk analysis, or related-work grounding
---

# Literature Grounding

Turn a rough topic into a field map, closest-work view, and novelty-risk assessment.

## Hard Gate

Do not make strong novelty or positioning claims before identifying the closest relevant prior work.

## Checklist

1. Clarify the exact question, task, and evidence bar
2. Gather the most relevant prior work, preferring closest papers over broad volume
3. Group the literature into 2-4 approach families
4. Identify the closest 3-8 papers or systems
5. Extract the key tension: what they solve, where they fail, and what remains open
6. Define the failure boundary and novelty risk
7. Present a field map and recommendation
8. Write the grounding note to `docs/paperpowers/specs/YYYY-MM-DD-<topic>-literature.md` when the work is substantial

## Required Output

Every grounding pass should try to produce:

- research question
- closest prior work
- approach families
- consensus points
- unresolved tension
- failure boundary
- novelty risk assessment
- implications for our direction

## Key Rules

- Prefer closest competitors over famous but distant papers
- Distinguish peer-reviewed work from preprints when it matters
- Separate observed facts from your interpretation
- If the search is incomplete, say it is incomplete
- If the idea looks crowded, say so directly

## Success Condition

The user leaves knowing what can be claimed, what cannot be claimed yet, and where the real opening might be.
```

- [ ] **Step 2: Verify `literature-grounding`**

Run: `test -f skills/literature-grounding/SKILL.md && ! test -f skills/literature-grounding/.gitkeep && rg -n "^name: literature-grounding$|^# Literature Grounding$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/literature-grounding/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `literature-grounding`**

```bash
git add skills/literature-grounding/SKILL.md
git commit -m "skills: add literature-grounding"
```

## Task 3: Author `hypothesis-to-validation`

**Files:**
- Create: `skills/hypothesis-to-validation/SKILL.md`
- Delete: `skills/hypothesis-to-validation/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/hypothesis-to-validation/SKILL.md`**

Write this content:

```markdown
---
name: hypothesis-to-validation
description: Use when a research direction exists and needs the cheapest credible validation plan
---

# Hypothesis to Validation

Turn a direction into minimum-cost falsification tests.

## Hard Gate

Do not jump from a promising idea straight into a full experiment matrix.

## Checklist

1. Restate the thesis and dominant claim
2. Identify what must be true for the idea to matter
3. List the main failure modes
4. Propose 2-3 validation routes
5. Recommend the cheapest decisive route
6. Define the minimal setup, baseline, metric, and pass-fail signal
7. State what to do if the test passes, fails, or is ambiguous
8. Write the validation note to `docs/paperpowers/plans/YYYY-MM-DD-<topic>-validation.md` when the work is substantial

## Required Output

Every validation plan should include:

- dominant claim
- assumption under test
- minimal setup
- necessary baseline
- decisive metric
- pass signal
- fail signal
- runtime or cost budget
- next action after the result

## Key Rules

- Prefer one decisive test per core claim
- Toy settings and ablations are acceptable if they answer the question faster
- Avoid benchmark shopping before the mechanism is credible
- Define stopping rules before expansion
- If the claim is too vague to test, force a sharper claim first

## Success Condition

The user leaves with a cheap plan that can falsify a weak direction before major implementation or compute investment.
```

- [ ] **Step 2: Verify `hypothesis-to-validation`**

Run: `test -f skills/hypothesis-to-validation/SKILL.md && ! test -f skills/hypothesis-to-validation/.gitkeep && rg -n "^name: hypothesis-to-validation$|^# Hypothesis to Validation$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/hypothesis-to-validation/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `hypothesis-to-validation`**

```bash
git add skills/hypothesis-to-validation/SKILL.md
git commit -m "skills: add hypothesis-to-validation"
```

## Task 4: Author `paper-planning`

**Files:**
- Create: `skills/paper-planning/SKILL.md`
- Delete: `skills/paper-planning/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/paper-planning/SKILL.md`**

Write this content:

```markdown
---
name: paper-planning
description: Use when results exist and the user needs a paper story, section outline, or claim-evidence plan before drafting
---

# Paper Planning

Turn experiment state into a coherent paper structure before polished writing begins.

## Hard Gate

Do not draft polished paper prose before reconciling claims, evidence, and gaps.

## Checklist

1. Inspect the current results, notes, and review feedback
2. Extract the one-sentence contribution
3. List the 2-4 claims the paper can currently support
4. Build a claim-evidence matrix
5. Identify weak or missing support and cut or weaken claims as needed
6. Choose the paper shape and section order
7. Plan figures, tables, and missing evidence
8. Write the paper plan to `docs/paperpowers/plans/YYYY-MM-DD-<topic>-paper.md`
9. Ask the user to review the outline before moving to `paper-writing`

## Required Output

Every paper plan should include:

- one-sentence contribution
- claim-evidence matrix
- section outline
- figure and table plan
- missing evidence list
- risk notes for reviewer pushback

## Key Rules

- One paper should tell one coherent story
- Cut unsupported claims before improving prose
- Front-load the most important result and positioning
- Distinguish what is already shown from what is only hoped for
- If the current results do not support a paper-worthy story, say so clearly

## Success Condition

The user leaves with a paper outline that is structurally sound, evidence-aware, and ready for drafting rather than wishful narration.
```

- [ ] **Step 2: Verify `paper-planning`**

Run: `test -f skills/paper-planning/SKILL.md && ! test -f skills/paper-planning/.gitkeep && rg -n "^name: paper-planning$|^# Paper Planning$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/paper-planning/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `paper-planning`**

```bash
git add skills/paper-planning/SKILL.md
git commit -m "skills: add paper-planning"
```

## Self-Review

### Spec coverage

- Literature grounding: covered by Task 2
- Minimal validation planning: covered by Task 3
- Results-to-paper planning: covered by Task 4
- Repo capability accuracy: covered by Task 1

No spec gap remains for this second-wave scope.

### Placeholder scan

Run:

```bash
python - <<'PY'
from pathlib import Path

text = Path("docs/paperpowers/plans/2026-03-28-second-wave-core-skills.md").read_text()
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

- Skill names match directory names
- Output paths follow `docs/paperpowers/specs` and `docs/paperpowers/plans`
- README wording matches the actual implemented skill set after this wave
