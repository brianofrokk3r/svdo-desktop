# Creating useful tickets

[README](../README.md) · [Usage wiki](../wiki/Home.md) · [Open a ticket](https://github.com/brianofrokk3r/svdo-desktop/issues/new/choose)

This repository is primarily for creating and tracking SVDO Desktop tickets.
Search [open and closed tickets](https://github.com/brianofrokk3r/svdo-desktop/issues)
first, then add useful context to an existing ticket or create a focused new one.
Use one ticket per independently verifiable problem or outcome.

## Include in every ticket

- A specific title that describes the problem or desired outcome.
- Why the issue matters and what task you were trying to complete.
- The affected area, such as installation, workspace setup, tickets, agent runs,
  git, Cloud sync, settings, or desktop notifications.
- The SVDO version, available from the installed package or release information.
- Operating system and version, CPU architecture, and install method.
- Relevant agent CLI and version, selected model/provider, and whether the
  workspace is a git repository when those facts affect the report.
- Sanitized screenshots, logs, or a minimal example when they clarify the issue.

Remove API keys, access tokens, private repository URLs, personal data, customer
content, and other secrets. Prefer pasted text over screenshots for error output
so it can be searched. Format commands and logs in fenced code blocks.

## Bug reports

A maintainer should be able to reproduce the failure without guessing. Include:

1. Preconditions and relevant configuration.
2. The smallest numbered sequence of actions that triggers the problem.
3. What you expected to happen.
4. What actually happened, including the complete sanitized error.
5. Whether it happens every time and the last version known to work.
6. Impact and any safe workaround you found.

Copy this outline into the ticket:

```markdown
## Context
[What were you trying to accomplish?]

## Steps to reproduce
1. ...
2. ...
3. ...

## Expected behavior
[Observable result you expected]

## Actual behavior
[Observable result, error, and frequency]

## Environment
- SVDO version:
- Install method: shell installer / npm / Bun / other
- OS and version:
- CPU architecture:
- Agent CLI and version (if relevant):
- Workspace/git details (if relevant):

## Evidence
[Sanitized logs, screenshots, or minimal reproduction]

## Impact or workaround
[Who is blocked, severity, and any workaround]
```

## Feature requests

Describe the problem before prescribing an interface. Include:

- The user or role with the need and a representative use case.
- Current behavior and why it is insufficient.
- The desired observable behavior or outcome.
- Alternatives or workarounds already considered.
- Constraints, dependencies, compatibility concerns, or out-of-scope behavior.
- Acceptance criteria when the requested result needs an objective boundary.

Copy this outline into the ticket:

```markdown
## Problem
[Who has what need, and why?]

## Use case
[A concrete example]

## Desired behavior
[Describe the observable outcome]

## Alternatives considered
[Current workaround or other approaches]

## Acceptance criteria
- [ ] Given ..., when ..., then ...
- [ ] ...

## Environment or constraints
[Platforms, integrations, compatibility, dependencies, or scope boundaries]
```

Acceptance criteria should describe externally observable results rather than an
implementation. They are especially useful for cross-platform behavior,
migrations, multi-step workflows, and requests with explicit exclusions. For an
early idea, state which parts still need discovery instead of inventing details.

## Documentation tickets

Name the page and heading, explain what is missing or inaccurate, and link the
source. Installation or compatibility corrections should include evidence from
a current release or source behavior. Broader usage improvements belong in the
[wiki source](../wiki/Home.md), while install and compatibility corrections may
affect the [README](../README.md).
