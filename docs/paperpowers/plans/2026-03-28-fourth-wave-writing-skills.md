# Fourth-Wave Writing-Skills Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the last reserved placeholder with a `paperpowers`-specific `writing-skills` meta-skill and update repository docs so the full V1 skill surface is represented accurately.

**Architecture:** Keep this wave small. Add one internal meta-skill that teaches how to create or revise `paperpowers` skills, verify they trigger correctly, and keep them concise. Then update the README so it no longer describes any remaining reserved V1 skill directory.

**Tech Stack:** Markdown, Git, shell verification

---

## File Structure

### Capability docs

- Modify: `README.md`

Responsibilities:

- `README.md` should reflect that the V1 skill set is now fully represented in the repo.

### New skill

- Create: `skills/writing-skills/SKILL.md`
- Delete: `skills/writing-skills/.gitkeep`

Responsibilities:

- `writing-skills` should teach contributors how to create, revise, and verify `paperpowers` skills without bloating them.

## Task 1: Update Repository Capability Summary

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Update `README.md` initial scaffold section**

Replace the current "eight foundational skills" block with:

```markdown
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
```

- [ ] **Step 2: Update `README.md` status sentence**

Use this paragraph:

```markdown
The repository is in its scaffold milestone. The current version documents the full V1 skill surface for `paperpowers`, covering idea shaping, literature grounding, minimum-cost validation planning, paper planning, section drafting, rebuttal preparation, research verification, and internal skill evolution.
```

- [ ] **Step 3: Verify `README.md` capability summary**

Run: `rg -n "nine foundational skills|writing-skills|full V1 skill surface|internal skill evolution" README.md`

Expected: matches for all additions

- [ ] **Step 4: Commit README capability update**

```bash
git add README.md
git commit -m "docs: update readme for writing-skills"
```

## Task 2: Author `writing-skills`

**Files:**
- Create: `skills/writing-skills/SKILL.md`
- Delete: `skills/writing-skills/.gitkeep`

- [ ] **Step 1: Replace `.gitkeep` with `skills/writing-skills/SKILL.md`**

Write a compact skill with:

- frontmatter `name: writing-skills`
- title `# Writing Skills`
- sections:
  - `## Hard Gate`
  - `## Checklist`
  - `## Required Output`
  - `## Key Rules`
  - `## Success Condition`

Content requirements:

- It must apply to creating or editing `paperpowers` skills
- It must require verifying trigger quality, workflow clarity, and output discipline
- It must emphasize concise scope and avoid turning skills into project narratives

- [ ] **Step 2: Verify `writing-skills`**

Run: `test -f skills/writing-skills/SKILL.md && ! test -f skills/writing-skills/.gitkeep && rg -n "^name: writing-skills$|^# Writing Skills$|^## Hard Gate$|^## Checklist$|^## Required Output$|^## Success Condition$" skills/writing-skills/SKILL.md`

Expected: exit code 0 and matches for all six patterns

- [ ] **Step 3: Commit `writing-skills`**

```bash
git add skills/writing-skills/SKILL.md
git commit -m "skills: add writing-skills"
```

## Self-Review

### Spec coverage

- Final reserved meta-skill: covered by Task 2
- Repo capability accuracy: covered by Task 1

No spec gap remains for this fourth-wave scope.

### Placeholder scan

Run:

```bash
python - <<'PY'
from pathlib import Path

text = Path("docs/paperpowers/plans/2026-03-28-fourth-wave-writing-skills.md").read_text()
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

- Skill name matches directory name
- README wording matches the implemented skill set after this wave
