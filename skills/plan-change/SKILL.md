---
name: plan-change
description: Plan an approved feature, refactor or bug fix before implementing it. Use after /grill for features, or directly for refactors and bugs.
---

1. Read `docs/requirements.md`, the feature files the work touches, the approved design if there's UI, `docs/architecture.md`, the project `CLAUDE.md` and the relevant code. If UI work has no approved design, run `/design-ui` first.
2. If the work needs a new or changed architecture or tech stack decision, stop and bring Paul options with trade-offs and a recommendation. Record his decision in `docs/architecture.md` before planning further.
3. Write the plan to `docs/work/<NNN-slug>.md` (next number, status `planned`), listing the features it touches. Keep it short: the behavior that changes, the approach, the tests (behavior and business logic; e2e only if a core journey is touched), and any implementation choice that affects a requirement.
4. Show Paul only what he needs: the behavior change and any requirement-affecting choices. Keep implementation detail out of the summary unless he asks.
5. For large or risky work (rebuilds, auth, data model, payments, anything public-facing), offer a red-team: spawn a fresh-context subagent with only the plan and requirements, ask it to find gaps, contradictions and overbuilding, then revise.
6. Get Paul's go-ahead before implementing, then set status to `in progress`.
