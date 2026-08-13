# Getting Started

Use the [README](../README.md) to choose an installation path and confirm
compatibility before continuing.

## Verify and launch

```sh
svdo --help
svdo desktop
```

`svdo desktop` launches the packaged Electron application and its app-owned
local runtime. If you prefer the local browser experience, `svdo start` starts
the service and `svdo open` opens its board.

## Initialize a workspace

From the git repository you want SVDO to manage:

```sh
cd /path/to/project
svdo init
```

During setup, choose the installed agent CLI that should run work. New
workspaces use the Speckit methodology by default. Workspace configuration is
scoped to the selected directory; confirm the path before initializing.

Open the workspace and check its state:

```sh
svdo open
svdo status
```

The desktop runtime may use a dynamically selected local port. The CLI discovers
that running instance automatically; you do not need to copy its port into the
workspace.

## First useful loop

1. Select the workspace on the board.
2. Create a small ticket with a verifiable outcome.
3. Attach or create the intended git branch when code changes are involved.
4. Start the appropriate ticket or methodology run.
5. Review streamed output and resulting files before accepting the work.

For concepts and board organization, continue to
[Workspaces and Boards](Workspaces-and-Boards.md).

---

[← Wiki home](Home.md) · [Next: Workspaces and Boards →](Workspaces-and-Boards.md)
