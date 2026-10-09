---
name: grill
description: Stress-test a proposed feature or requirement change with Paul before planning. Use for new features or changes to docs/requirements.md or docs/features/, or when Paul says "grill".
---

Grill Paul about the proposal until the requirement is clear, justified and minimal.

1. Read `docs/requirements.md`, the feature docs the proposal touches, and the global standards.
2. Ask one question at a time, each with your recommended answer. Cover:
   - **Use case:** who uses this, and when? If the answer is vague, push for a real person and moment, or suggest cutting it.
   - **Simplicity:** what's the smallest version that solves the use case? What can be deferred?
   - **Fit:** does it contradict or overlap an existing requirement or feature? Is it consistent with the app's character?
   - **Profile:** does it change the project's profile or expected scale?
3. Stop when there are no open questions. Propose the exact diff to `docs/requirements.md` and any feature docs, and wait for approval before writing it. Once it's settled, ask whether Paul wants a red-team (a checkpoint in the standards).

Don't discuss implementation unless it changes a requirement.
