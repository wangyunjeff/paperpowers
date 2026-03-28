# Third-Wave Writing and Rebuttal Skills Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add the remaining user-facing V1 workflow skills for paper drafting and rebuttal preparation so `paperpowers` can cover the full research path from idea shaping to paper planning to response strategy.

**Architecture:** Keep the implementation compact and skill-first. Fill the two reserved directories with concise but opinionated workflow guides, then update repository messaging so the README reflects that the paper-production side is now partially implemented beyond planning.

**Tech Stack:** Markdown, Git, shell verification

---

## File Structure

### Capability docs

- Modify: `README.md`

Responsibilities:

- `README.md` should accurately describe the expanded implemented skill set and the current scaffold status.

### New skills

- Create: `skills/paper-writing/SKILL.md`
- Create: `skills/rebuttal-prep/SKILL.md`
- Delete: `skills/paper-writing/.gitkeep`
- Delete: `skills/rebuttal-prep/.gitkeep`

Responsibilities:

- `paper-writing` must force drafting after planning, with strong claim-fidelity and evidence-aware writing constraints.
- `rebuttal-prep` must turn review comments into issue classification, decision logic, and response strategy rather than emotional patchwork.

## Task 1: Update Repository Capability Summary

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Update `README.md` implemented skills count**

Replace the current "six foundational skills" block with:

```markdown
- eight foundational skills:
  - `using-paperpowers`
  - `research-brainstorming`
  - `literature-grounding`
  - `hypothesis-to-validation`
  - `paper-planning`
  - `paper-writing`
  - `rebuttal-prep`
  - `research-verification`
- a reserved directory for the remaining V1 meta-skill
```

- [ ] **Step 2: Update `README.md` status sentence**

Use this paragraph:

```markdown
The repository is in its scaffold milestone. The current version already implements the core user-facing V1 workflow from idea shaping through literature grounding, minimum-cost validation planning, paper planning, section drafting, and rebuttal preparation, while the internal meta-skill `writing-skills` is still reserved for a later pass.
```

- [ ] **Step 3: Verify `README.md` capability summary**

Run: `rg -n "eight foundational skills|paper-writing|rebuttal-prep|remaining V1 meta-skill|core user-facing V1 workflow" README.md`

Expected: matches for all additions

- [ ] **Step 4: Commit README capability update**

```bash
git add README.md
git commit -m "docs: update readme for writing and rebuttal skills"
```

## Task 2: Author `paper-writing`

**Files:**
- Create: `skills/paper-writing/SKILL.md`
- Delete: `skills/paper-writing/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/paper-writing/SKILL.md`**

Write a compact skill with:

- frontmatter `name: paper-writing`
- title `# Paper Writing`
- sections:
  - `## Hard Gate`
  - `## Checklist`
  - `## Required Output`
  - `## Key Rules`
  - `## Success Condition`

Content requirements:

- It must require `paper-planning` before drafting
- It must focus on section drafting, claim fidelity, evidence alignment, and cutting overstatements
- It must forbid polished prose from outrunning the evidence

- [ ] **Step 2: Verify `paper-writing`**

Run: `test -f skills/paper-writing/SKILL.md && ! test -f skills/paper-writing/.gitkeep && rg -n "^name: paper-writing$|^# Paper Writing$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/paper-writing/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `paper-writing`**

```bash
git add skills/paper-writing/SKILL.md
git commit -m "skills: add paper-writing"
```

## Task 3: Author `rebuttal-prep`

**Files:**
- Create: `skills/rebuttal-prep/SKILL.md`
- Delete: `skills/rebuttal-prep/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/rebuttal-prep/SKILL.md`**

Write a compact skill with:

- frontmatter `name: rebuttal-prep`
- title `# Rebuttal Prep`
- sections:
  - `## Hard Gate`
  - `## Checklist`
  - `## Required Output`
  - `## Key Rules`
  - `## Success Condition`

Content requirements:

- It must classify reviewer comments
- It must distinguish concede vs rebut vs new evidence needed
- It must focus on response strategy before polished response prose

- [ ] **Step 2: Verify `rebuttal-prep`**

Run: `test -f skills/rebuttal-prep/SKILL.md && ! test -f skills/rebuttal-prep/.gitkeep && rg -n "^name: rebuttal-prep$|^# Rebuttal Prep$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/rebuttal-prep/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `rebuttal-prep`**

```bash
git add skills/rebuttal-prep/SKILL.md
git commit -m "skills: add rebuttal-prep"
```

## Self-Review

### Spec coverage

- Paper drafting after planning: covered by Task 2
- Rebuttal strategy before prose: covered by Task 3
- Repo capability accuracy: covered by Task 1

No spec gap remains for this third-wave scope.

### Placeholder scan

Run:

```bash
python - <<'PY'
from pathlib import Path

text = Path("docs/paperpowers/plans/2026-03-28-third-wave-writing-and-rebuttal.md").read_text()
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
- README wording matches the implemented skill set after this wave
- The remaining reserved skill is only `writing-skills`
