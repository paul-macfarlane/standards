---
name: review-change
description: Review completed work against the requirements and the global standards, then summarize it for Paul. Use after implementing a feature, refactor or bug fix.
---

Review in a fresh-context subagent on two axes, then fix what it finds before reporting:

- **Spec:** does the change do what `docs/requirements.md`, the feature docs, the approved design and the work package say, and nothing more? Flag any unrequested feature or scope creep.
- **Standards:** check against `docs/architecture.md` (no unapproved stack or structural changes) and the goals and engineering practice in the standards. Doc or feature changes this reveals (repeated text, overlapping features) are proposals for Paul, not fixes.

Ask whether Paul wants a red-team before merge (a checkpoint in the standards). Then give Paul the summary from the standards.

Once Paul approves the requirement changes, make sure they're in `docs/requirements.md` or `docs/features/`, then delete the work package file.
