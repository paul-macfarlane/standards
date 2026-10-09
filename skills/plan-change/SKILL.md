---
name: plan-change
description: Plan an approved feature, refactor or bug fix before implementing it. Use after /grill for features, or directly for refactors and bugs.
---

1. Read `docs/requirements.md`, the feature docs the work touches, the approved design if there's UI, `docs/architecture.md`, the project `CLAUDE.md` and the relevant code. If UI work has no approved design, run `/design-ui` first.
2. If the work needs a new or changed architecture or tech stack decision, stop and bring Paul options with trade-offs and a recommendation. Record his decision in `docs/architecture.md` before planning further.
3. Write the plan to `docs/work/<NNN-slug>.md` (next number, status `planned`), listing the features it touches. Keep it short: the behavior that changes, the approach, the tests (behavior and business logic; e2e only if a core journey is touched), and any implementation choice that affects a requirement.
4. Show Paul only what he needs: the behavior change and any requirement-affecting choices. Keep implementation detail out of the summary unless he asks.
5. Ask about a red-team if the work hits a red-team checkpoint in the standards. If Paul says yes, revise the plan with what it finds.
6. Get Paul's go-ahead before implementing, then set status to `in progress`.
