---
name: design-ui
description: Design the screens for a feature in Claude Design before any UI code is written. Use after /grill for features with UI, or whenever UI work has no approved design.
---

1. Read `docs/requirements.md` (character, design links) and the feature files involved.
2. If the app has no design system yet, create one first in Claude Design from the app's character: colors, type, spacing and the few components it needs. Get Paul's approval and add the link to `docs/requirements.md`.
3. Mock the screens the work touches in Claude Design, using the app's design system. Mobile first, then wider viewports. Show the states that matter: empty, loading, error, typical data.
4. Direction comes from Paul. Build what he described; propose alternatives only when they clearly help the problem, and label them as proposals.
5. Check against the standards before showing it: simple, accessible, consistent within the app, no AI slop.
6. Get Paul's approval, then add the screen links to the Design section of `docs/requirements.md`. Implementation must match the approved design; any deviation goes back to Paul.
