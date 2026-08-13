# Git and Review Workflows

## Branches and ticket worktrees

A ticket can attach an existing branch before an isolated worktree is created.
Once ready, the ticket worktree lets agent work proceed without switching the
primary checkout. Confirm the displayed branch and worktree state before a run.

SVDO does not silently remove or recreate a dirty worktree or one used by an
active run. Review and preserve local changes, wait for the active run, or make
the cleanup decision explicitly.

## Review changes

Before handoff:

1. Read the diff, including generated and untracked files.
2. Run checks appropriate to the changed behavior.
3. Confirm ticket acceptance criteria and document anything deferred.
4. Commit a coherent set of changes on the intended branch.
5. Use the configured hosted review handoff when a pull request is needed.

External review links open in the system browser after desktop validation. If a
handoff fails, preserve the branch and open the hosting service directly rather
than repeating mutations blindly.

## Resolve conflicts

The Git sidebar can surface text conflicts and supports saving resolutions for
files it can safely represent. Review both current and incoming content before
saving, then continue the merge or rebase only after all required conflicts are
resolved.

Binary, delete/modify, rename/delete, submodule, and other structural conflicts
require manual git tools. If the application cannot complete a conflict action,
copy the sanitized error, inspect `git status` in the affected worktree, and
avoid deleting the worktree as a first response.

---

[← Tickets and Agent Runs](Tickets-and-Agent-Runs.md) · [Wiki home](Home.md) · [Next: Settings and Integrations →](Settings-and-Integrations.md)
