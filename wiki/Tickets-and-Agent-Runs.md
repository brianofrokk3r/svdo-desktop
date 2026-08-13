# Tickets and Agent Runs

## Choose a workflow

- Use a **Quick Run** when the ticket is already concrete and does not need
  separate planning artifacts.
- Use **Speckit** when work benefits from an explicit specification, plan, task
  breakdown, and implementation sequence.
- Use a configured **Agent** for reusable project-specific instructions.

A ticket prompt should describe the outcome, scope, constraints, evidence, and
acceptance criteria. It should not rely on unstated conversation history.

## Before starting

1. Confirm the selected workspace and ticket.
2. Review the ticket's scope and acceptance criteria.
3. Confirm the agent CLI, model/provider, and any required authentication.
4. Check the target branch or ticket worktree and preserve unrelated changes.
5. Remove secrets and unnecessary personal data from prompts and attachments.

## During and after a run

SVDO streams agent output into ticket details and keeps run progress associated
with the ticket. A run can complete, fail, or be stopped. Desktop notifications
are best-effort; the in-app completion message is the reliable place to return
to the related ticket.

Agent output is evidence, not automatic approval. Inspect the changed files,
run the relevant checks, compare the result with acceptance criteria, and record
follow-up work. If a run fails, keep the exact sanitized error and the last
successful step for diagnosis.

## Structured Speckit runs

Speckit work proceeds through specification, planning, task breakdown, and
implementation. Read each artifact before progressing. If the work changes
materially, update the relevant artifact so the task list and implementation do
not describe different outcomes.

Continue to [Git and Review Workflows](Git-and-Review-Workflows.md) when a ticket
uses a branch or isolated worktree.

---

[← Workspaces and Boards](Workspaces-and-Boards.md) · [Wiki home](Home.md) · [Next: Git and Review Workflows →](Git-and-Review-Workflows.md)
