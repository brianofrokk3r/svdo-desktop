# Tickets and Agent Runs

## Choose a workflow

- Use a **Quick Run** when the ticket is already concrete and does not need
  separate planning artifacts.
- Use **Speckit** when work benefits from an explicit specification, plan, task
  breakdown, and implementation sequence.
- Use a configured **Agent** for reusable project-specific instructions.

A ticket prompt should describe the outcome, scope, constraints, evidence, and
acceptance criteria. It should not rely on unstated conversation history.

## What an Agent is

An **Agent** is a named, reusable instruction bundle. Its system prompt describes
the role or job to perform, and its review scope controls how broadly an
automation review may inspect work. An Agent can also have reusable automation
templates or an inbound trigger.

An Agent is not the command-line tool that performs the work. Each workspace
selects an installed CLI/provider, such as Codex, Copilot, Claude, or LiteLLM.
When you run an Agent, SVDO combines the Agent instructions with the current
workspace and run context, then uses that workspace CLI and its configured model.
Changing workspaces can therefore change which CLI executes the same reusable
Agent.

Agents may be Local-only, locally synchronized, or Cloud-managed. Ownership and
sync badges in Desktop show whether you can edit, duplicate, or synchronize a
resource. Local Agents are not uploaded unless synchronization is explicitly
enabled.

## How Agents relate to tickets and projects

Quick Run and Speckit are ticket workflows: they start from a ticket and keep
progress and results associated with it. A saved Agent can also be run manually
from the **Agents** view for the active workspace, or selected by a stage
automation that runs when a ticket moves between configured stages. In ticket
comments, mentioning an available Agent by its `@handle` starts a run with the
ticket, comment, and Agent instructions as context; the resulting activity stays
on that ticket.

For automation reviews, choose the narrowest appropriate scope:

- **Ticket-Scoped** keeps the review focused on the active ticket's worktree,
  branch, changed files, or equivalent ticket-specific changes.
- **Project-Scoped** may inspect broader repository context. Findings unrelated
  to the active ticket are separated as suggested follow-up work and require
  approval before they become tickets.

The scope changes what an Agent may review; it does not move a ticket run out of
its workspace or detach its output from the related ticket.

## Run an Agent in Desktop

1. Select the workspace whose CLI and repository context should be used.
2. Open **Agents** and review the Agent's prompt, scope, ownership, and sync
   state.
3. Choose **Run**. If it is unavailable, resolve the displayed workspace, CLI,
   authentication, or resource-state condition first.
4. Follow progress in the run panel. For ticket or automation runs, return to
   the ticket activity to inspect results and suggested follow-up work.
5. Review changed files and checks before accepting the output. An Agent run is
   evidence, not automatic approval.

For creating and maintaining Agent definitions, see
[Settings and Integrations](Settings-and-Integrations.md#agents).

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
