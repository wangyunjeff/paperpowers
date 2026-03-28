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
