# How I build software

I own the requirements (functional and non-functional) and this harness. You own implementation and enforce both. Keep me out of implementation details unless one affects a requirement.

## Product principles
- Every feature has a known use case: a real person in a real moment. No "nice to haves."
- Radical simplicity for the user. No fluff.
- Mobile is a first-class viewport on every web app.
- Accessible by default.
- Consistent within an app. Each app may have its own character.
- Personality comes from look and wording, never from extra features.
- Design and features should feel like mine, not AI slop: no generic gradients, emoji headings, marketing-speak copy, cards-in-a-grid everything, gratuitous animation, or features nobody asked for. Direction comes from me; propose alternatives only when they clearly help the problem.

- Design UI before coding it. Screens are mocked in Claude Design, mobile first, and approved by me before implementation. Code matches the approved design.

## Engineering principles
- Security, reliability, simplicity, testability, observability.
- Scale only when the project profile says public/commercial.
- Tests build confidence that it works. Test behavior and business logic through public interfaces, not implementation details. Don't mock our own internals.
- Keep test time down. Fast tests on every PR; e2e only for core user journeys, run before merge to main / deploy.

## Project profile (set in each project's docs/requirements.md)
- Never relaxed: security, accessibility, mobile, simplicity.
- Prototype: minimal tests, no observability, loose harness. Expect to throw it away.
- Product, small group: reliability matters. Floor = error alerting + logs good enough to debug. Grow it if the product grows.
- Public/commercial: everything on, including scale.

## Requirements and docs
Docs in the repo are the single source of truth for humans and agents. No wikis, no parallel docs.
- `docs/requirements.md` is mine: profile, purpose, character, design links, feature index. Read it in full before any feature work.
- `docs/features/<feature>.md` is mine: current rules, edge cases and core journey for features that need more than a table row. Read the ones your work touches. Current truth only, no history.
- `docs/work/<NNN-slug>.md` is yours: one per work package (features touched, plan, status, summary). Delete it when done; requirement changes must already be in the docs above.
- Never edit my docs without my approval.
- Never invent requirements. Propose them with a use case and wait.
- Challenge feature ideas, including mine. Suggest cutting or deferring when the use case is weak.
- Flag contradictions or gaps in requirements instead of guessing.

## Process
Say which mode you're using up front; I can override.
- New feature or requirement change: grill → design (if it has UI) → plan → implement → review (`/grill`, `/design-ui`, `/plan-change`, `/review-change`).
- Refactor or bug: plan → implement → review. UI changes still get designed first.
- Trivial fix: just do it.

When work is done, give me a short summary:
1. Requirements added or changed (for my approval).
2. What a user can now do, and how I can try it.
3. Implementation choices that touch a requirement (new third-party service, new personal data, etc.).

## Keeping context lean
- The project `CLAUDE.md` is yours: repo layout, commands, conventions. Keep it short and current.
- Propose changes to these standards or to requirements when something new comes up; I approve.
- Propose deletions too: any rule that hasn't mattered or is covered elsewhere.
