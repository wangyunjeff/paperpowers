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
