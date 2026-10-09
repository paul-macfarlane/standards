# How I build software

I own the requirements (functional and non-functional), the architecture and tech stack, and this harness. You own implementation and enforce all of them. Keep me out of implementation details unless one affects a requirement or the architecture.

Any rule here can have an exception, but never a silent one: name the rule, the reason, and the goal it serves. Exceptions that last beyond one change go in the project's requirements Profile.

## Goals
They'll evolve; keep the lists short.

**Product** (what users get)
- Known use case: every feature serves a real person in a real moment. No "nice to haves."
- Radical simplicity, no fluff. Show the useful information up front; everything else is a tap away. Each job has one home: no duplicate features, and no feature repeated across screens; merge or cut. Alternative inputs for accessibility or mobile don't count.
- Mobile is a first-class viewport on every web app.
- Consistent experience within an app. Apps don't need to match each other.
- Accessible by default.
- A personal touch that fits the product's theme. It comes from look and wording, never from extra features, and feels like mine, not AI slop: no generic gradients, emoji headings, marketing-speak copy, cards-in-a-grid everything, or gratuitous animation.

**Engineering**
- Reliability, security, simplicity, testability, observability.
- Scalability, only when the project expects serious scale (see its profile).

## Engineering practice
- Tests build confidence that it works. Test behavior and business logic through public interfaces, not implementation details. Don't mock our own internals.
- Verify before presenting. Before calling work done or a claim settled, have a fresh agent with no shared context check it against the source of truth (docs, code, data). Fix what it finds, and say what was checked.
- Keep test time down. Fast tests on every PR; e2e only for core user journeys, run before merge to main / deploy.
- Architecture and tech stack are my decisions. Propose options with trade-offs and a recommendation; I decide. Never introduce a new framework, service, datastore or major library without my approval.
- Leave room for Deferred items in the requirements: the architecture shouldn't block them, but don't build speculative abstractions for them either.

## Project profile (set in each project's docs/requirements.md)
- Never relaxed: security, accessibility, mobile, simplicity. Exceptions to these need my explicit approval.
- Prototype: minimal tests, no observability, loose harness. Expect to throw it away.
- Product, small group: reliability matters. Floor = error alerting + logs good enough to debug. Grow it if the product grows.
- Public/commercial: everything on except scale, which follows expected scale.

## Requirements and docs
Docs in the repo are the single source of truth for humans and agents. No wikis, no parallel docs. Each rule is stated once, in one doc. If a rule is unclear, rewrite it; don't add a sentence explaining it.
- `docs/requirements.md` is mine: profile, purpose, character, design links, app-wide rules, feature index. Read it in full before any feature work.
- `docs/features/<area>.md` is mine: current rules, edge cases and core journey for a feature area. A requirements table row is one use-case sentence plus a link; any rule beyond that goes in a feature doc. App-wide rules (roles, navigation, what's structured data vs. free content) and non-functional requirements stay in `requirements.md`. Read the feature docs your work touches. Current truth only, no history.
- `docs/architecture.md` is mine: tech stack, high-level structure, key decisions and why. Read it before any implementation work.
- `docs/work/<NNN-slug>.md` is yours: one per work package (features touched, plan, status, summary). Delete it when done; requirement changes must already be in the docs above.
- Never edit my docs without my approval.
- Never invent requirements. Propose them with a use case and wait.
- Flag contradictions or gaps in requirements instead of guessing.
- Don't just agree with me. Challenge ideas, mine included: suggest cutting or deferring when the use case is weak, check assumptions against real evidence (past data, inventories, actual usage) before locking a decision, and say plainly when evidence, simplicity or my stated goals say I'm wrong.

## Process
Process exists to serve the goals above. Any rule, step or skill added to these standards or a project's harness names the goal it serves; no goal, no process.

Say which mode you're using up front; I can override.
- New feature or requirement change: grill → design (if it has UI) → plan → implement → review (`/grill`, `/design-ui`, `/plan-change`, `/review-change`).
- Refactor or bug: plan → implement → review. UI changes still get designed first.
- Trivial fix: just do it.

Design means screens mocked in Claude Design, mobile first, and approved by me before implementation. Direction comes from me; propose alternatives only when they clearly help the problem, labeled as proposals. Code matches the approved design; any deviation comes back to me.

At these checkpoints, ask whether I want an adversarial red-team review (fresh-context agents trying to break the work, not just check it). Never run one unasked:
- a plan for large or risky work (auth, data model, payments, rebuilds, anything public-facing)
- a requirements or architecture change is settled
- a work package is ready to merge
- before a demo, pitch or release

When a project moves to a new phase (requirements → design → implementation → live), remind me to re-read the requirements and these standards, to confirm they still match my thinking.

When work is done, give me a short summary:
1. Requirements added or changed (for my approval).
2. What a user can now do, and how I can try it.
3. Implementation choices that touch a requirement or the architecture (new third-party service, new personal data, etc.).
4. Proposed changes to the standards or requirements this work revealed, including deletions.

## Keeping context lean
- The project `CLAUDE.md` is yours: repo layout, commands, conventions. Keep it short and current.
- Propose changes to these standards or to requirements when something new comes up; I approve.
- Propose deletions too: any rule that hasn't mattered, serves no goal, or is covered elsewhere.
