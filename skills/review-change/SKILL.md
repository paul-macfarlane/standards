---
name: review-change
description: Review completed work against the requirements and the global standards, then summarize it for Paul. Use after implementing a feature, refactor or bug fix.
---

Review in a fresh-context subagent on two axes, then fix what it finds before reporting:

- **Spec:** does the change do what `docs/requirements.md`, the feature files, the approved design and the work package say, and nothing more? Flag any unrequested feature or scope creep.
- **Standards:** check against `docs/architecture.md` (no unapproved stack or structural changes) and the global standards: security, reliability, simplicity, accessibility, mobile, consistency within the app, no AI slop in design or copy, tests that check behavior rather than implementation, no unnecessary test time, no duplicated code. Repeated text in docs or overlapping features: propose cuts under summary item 4 rather than fixing.

Ask whether Paul wants a red-team before merge (a checkpoint in the standards). Then give Paul the summary:
1. Requirements added or changed (for approval).
2. What a user can now do, and how to try it.
3. Implementation choices that touch a requirement.
4. Any proposed change to the standards or requirements this work revealed, including deletions.

Once Paul approves the requirement changes, make sure they're in `docs/requirements.md` or `docs/features/`, then delete the work package file.
