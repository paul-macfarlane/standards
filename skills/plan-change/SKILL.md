---
name: plan-change
description: Plan an approved feature, refactor or bug fix before implementing it. Use after /grill for features, or directly for refactors and bugs.
---

1. Read `docs/requirements.md`, the project `CLAUDE.md` and the relevant code.
2. Write a short plan: the behavior that changes, the approach, the tests (behavior and business logic; e2e only if a core journey is touched), and any implementation choice that affects a requirement.
3. Show Paul only what he needs: the behavior change and any requirement-affecting choices. Keep implementation detail out of the summary unless he asks.
4. For large or risky work (rebuilds, auth, data model, payments, anything public-facing), offer a red-team: spawn a fresh-context subagent with only the plan and requirements, ask it to find gaps, contradictions and overbuilding, then revise.
5. Get Paul's go-ahead before implementing.
