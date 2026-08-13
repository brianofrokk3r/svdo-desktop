# Settings and Integrations

## Agent CLI and model settings

Choose an installed CLI provider during workspace setup. When that provider
supports model selection, enter its model/provider identifier in Workspace
Settings before starting ticket, Speckit, Agent, or automation runs. LiteLLM
also needs an API key; saved keys are masked in settings and supplied to the run
environment.

CLI authentication and repository-trust rules still apply. In particular, an
installed Codex CLI can remain selected while setup reports that the directory
is not trusted. Resolve the stated trust or repository condition rather than
assuming another provider was selected.

## Agents

Open **Agents** with a workspace selected to create and maintain reusable Agent
definitions. Each Agent has a name, system prompt, and ticket- or project-scoped
review setting. Depending on ownership and lifecycle state, its card also lets
you run, edit, duplicate, synchronize, write, or delete the resource. **Write
file** stores repository Markdown at a path you confirm; its default SVDO path
is `.joule/agents/<handle>.agent.md`. Imported repository-backed Agents can be
refreshed when their source Markdown changes.

The active workspace supplies the CLI/provider and model used to execute an
Agent. Agent definitions do not embed or replace that workspace selection. See
[Tickets and Agent Runs](Tickets-and-Agent-Runs.md#what-an-agent-is) for manual,
ticket, project-scope, and automation behavior.

For provider-neutral portable instructions, SVDO also recognizes Agent
definitions at `agents/<handle>.agent.md`. SVDO may compile provider-native
projections before a run when the selected CLI supports them. It leaves
unmanaged or manually diverged files unchanged, so review source warnings
instead of assuming a file was overwritten.

## Skills

A **Skill** is a reusable instruction module for a focused procedure, convention,
or capability. Agents and ordinary workspace runs can use Skills: in a supported
run composer, choose a Skill or type `/skill <handle>`. SVDO resolves that handle
and adds the Skill's content to that run. Ticket-selected Skills are ephemeral;
selecting one does not add it permanently to repository instructions or every
future run.

Open **Skills** to:

- Create a Local-only Skill with a name, handle, description, content, and
  category.
- Import supported Skill Markdown from the active repository.
- Edit resources that their ownership and lifecycle state allow you to edit.
- Refresh a repository-backed Skill after its source changes.
- Use **Write file** to persist a Skill to the selected repository.
- Filter Local-only, repository-backed, synchronized, and Cloud-managed
  resources and inspect their ownership or sync status.

**Write file** defaults to `.joule/skills/<handle>/SKILL.md`. For
provider-neutral portable instructions, SVDO also recognizes
`skills/<handle>/SKILL.md`; scripts, references, and assets used by the Skill
remain beside it. SVDO compiles or exposes provider-native files according to
the selected CLI's capabilities. Some providers support Skills natively while
others receive prompt-resolved content, so keep the selected repository Skill
file as the canonical source. Repository paths that escape the project,
including escaping symlinks, are rejected.

## Standards

Standards express conventions that future runs should follow. Apply only the
standards relevant to a workspace and keep their instructions specific enough
to verify. Reusable Agents and Skills can pair those conventions with repeatable
roles and procedures.

Local Agents, Skills, and Standards are not uploaded to Cloud unless explicitly
marked for synchronization. Review content and bundled files for secrets before
enabling sharing.

## Automations

Stage automations can launch agent templates, methodologies, or git actions when
a ticket moves between eligible stages. Before enabling one, verify:

- Its source and destination stages.
- The agent or methodology and required credentials.
- Whether repeated transitions are safe.
- What success and failure look like on the ticket.

## Cloud

SVDO Cloud is optional; Desktop/Local can operate standalone. When Cloud is
connected, organization, board, and shared-resource behavior depends on the
signed-in account and workspace configuration. Confirm the active organization
before changing shared resources.

---

[← Git and Review Workflows](Git-and-Review-Workflows.md) · [Wiki home](Home.md) · [Next: Troubleshooting →](Troubleshooting.md)
