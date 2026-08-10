# Keyball39 Agent Guidelines

These instructions apply to all work in this repository. Prefer a fast,
surgical workflow while protecting existing physical-key behavior.

## Choose the Workflow Before Editing

### Implement Directly

Use direct implementation when all of the following are true:

- The requested physical key, gesture, and output are explicit.
- The change is confined to a few bindings or configuration lines.
- No existing action must be removed, moved, or given a new hold/tap meaning.
- The change is reversible and has no meaningful layout trade-off.
- The user has said to implement, proceed, try it, or make the change.

For direct implementation:

1. Inspect the actual binding and current Git state once.
2. State the success criteria in one short update.
3. Make the smallest possible edit without offering layout alternatives,
   creating visuals, or writing a design document.
4. Run focused validation, commit the intended files, and push the current
   feature branch.
5. Report GitHub Actions as pending unless the user asked to wait for them or
   a successful remote build is necessary for the requested conclusion.

Examples include changing CPI, adjusting a timing value, adding one duplicate
symbol to an unused position, or applying an already approved mapping.

### Design the Full Layout First

Use a design discussion when any of the following are true:

- The user asks for suggestions, an overall design, or a posture review.
- The change affects layer activation, hold-tap behavior, combos, or several
  physical keys or layers.
- An existing Command, Option, Control, Shift, Enter, Backspace, Space,
  scrolling, mouse, or Bluetooth action could become harder to reach.
- Multiple reasonable layouts have materially different posture or behavior.
- The requested result is ambiguous or would remove an existing action.

For layout design:

1. Inspect the whole affected layer and every activation route.
2. Ask only one clarification at a time and only when the answer changes the
   design materially.
3. Present two or three complete options with concrete physical gestures and
   recommend one.
4. Use a visual comparison only when the user asks for it or accepts an offer
   made because the spatial relationship is genuinely difficult to explain.
5. Obtain approval once. After the user says to proceed, implement the approved
   design without reopening settled choices.

When the request is borderline, preserve every existing behavior and choose the
smallest reversible change. State the assumption briefly and implement it;
stop only if the unresolved choice could cause a real behavior conflict.

## Keyball39 Validation and Publication

- Keep each Keyball39 layer at exactly 39 bindings.
- Run `git diff --check` and inspect the focused keymap/configuration diff.
- For approved feature-branch code changes, stage only intended files, create a
  focused commit, and push automatically so the user can review on GitHub.
- Before pushing, check the live remote. If keymap-drawer advanced the branch,
  inspect it and fast-forward when safe. Never force-push.
- Do not alter CI workflows unless the user explicitly requests it.
- Distinguish repository, CI, and hardware state. A pushed or successful build
  does not mean the matching UF2 has been physically flashed and tested.

## Context, New Tasks, and Handoffs

Do not create a new user-owned task automatically. Recommend a new task when:

- The current objective is complete and the next request is independent.
- Several unrelated topics are making the active request ambiguous.
- The history is causing repeated rediscovery or conflicting assumptions.
- A short handoff would be clearer than carrying the remaining conversation.

Do not interrupt active implementation merely to save tokens. When recommending
a new task, first prepare a compact handoff containing:

- the objective and exact repository path;
- the branch plus local and remote HEADs;
- dirty files or confirmation that the worktree is clean;
- approved decisions and physical-key gestures;
- completed validation, CI status, and physical-flash status; and
- the single next action.

Only create, fork, or hand off to a new user-owned task after the user explicitly
asks. Do not use subagents as a context-compaction mechanism. Use them only for
concrete, independent work that can run in parallel and only when user or
applicable instructions authorize delegation.

When automatic context compaction provides a summary, continue from it instead
of repeating completed work. Re-check only state that can drift, such as the
branch, remote HEAD, CI result, worktree status, and installed firmware.
