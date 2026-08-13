# Workspaces and Boards

## Workspaces

A workspace binds a board, agent configuration, standards, and git operations
to a directory. Select the workspace you mean to change before creating tickets
or starting runs. Local agents and standards remain local unless they are
explicitly configured for Cloud synchronization.

The application needs continued access to registered workspace directories and
their git metadata. Moving or deleting a workspace outside SVDO can leave its
registration pointing at a missing path.

## Boards and stages

The board organizes tickets into ordered stages. Move a ticket as its real state
changes so its position remains useful to collaborators and automations. A stage
transition can run a configured agent, methodology, or git action; review the
workspace's automation rules before moving sensitive work.

## Tickets

Keep a ticket focused on one outcome. A useful working ticket normally has:

- A result-oriented title and enough context to understand the need.
- Acceptance criteria that can be checked after a run.
- Relevant dependencies or related work.
- A branch association when the work changes a git repository.
- Comments recording decisions that should survive beyond one agent session.

Epic-sized work can be broken into child story tickets. The Epic carries overall
planning and validation; each child should remain an executable slice with its
own progress.

Public product problems and requests belong in this repository's
[issue tracker](https://github.com/brianofrokk3r/svdo-desktop/issues), using the
[ticket creation guide](../docs/creating-tickets.md). Workspace tickets inside
the application track the work you run through SVDO.

## Local data

SVDO stores local application data, run records, workspace settings, and managed
worktrees on the computer. Treat workspace files and run output as project data:
review them before sharing and do not place secrets in ticket prompts.

---

[← Getting Started](Getting-Started.md) · [Wiki home](Home.md) · [Next: Tickets and Agent Runs →](Tickets-and-Agent-Runs.md)
