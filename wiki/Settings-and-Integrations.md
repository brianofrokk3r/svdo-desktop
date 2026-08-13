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

## Standards and reusable agents

Standards express conventions that future runs should follow. Apply only the
standards relevant to a workspace and keep their instructions specific enough
to verify. Reusable agents can pair those instructions with repeatable prompts.

Local agents and standards are not uploaded to Cloud unless explicitly marked
for synchronization. Review content for secrets before enabling sharing.

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
