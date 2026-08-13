# Troubleshooting

## `svdo` is not found

Open a new terminal and run `svdo --help`. If it is still unavailable, locate
your package manager's global binary directory and add it to `PATH`. Reinstall
only after confirming the original global install did not succeed.

## Installation fails

- For the shell installer, confirm macOS or Linux and a supported 64-bit
  architecture listed in the [README](../README.md).
- For npm, confirm `node --version` reports Node.js 24 or newer.
- For Bun, confirm `bun --version` works and global package installs are writable.
- npm deprecation warnings from transitive runtime packages are not by
  themselves a failure; use the installer's final status and exit result.
- Avoid `npm install -g joule`; that public registry name is unrelated.

The shell installer's anonymous telemetry records basic system configuration and
installation completion only to inform build compatibility; it does not measure
application usage. To disable it, run the installer with `SVDO_TELEMETRY=0` as
shown in the [README](../README.md).

## Desktop does not start

Run `svdo --help` first to separate installation from launch problems. If
`svdo init` says a discovered desktop runtime is unreachable, restart Desktop or
run `svdo start`. Record the complete sanitized terminal error if launch still
fails.

If you launched Desktop on a fixed port and that port is already in use, stop
the process using it or choose another port:

```sh
PORT=4102 svdo desktop
```

Omit `PORT` to let the packaged Desktop runtime choose an available loopback
port automatically. Do not pass `--backend-port` or `--frontend-port` to
`svdo desktop`; those flags configure the separate `svdo start` workflow.

## Agent run cannot start

Confirm the selected CLI is installed and authenticated, its configured model
identifier is valid, and the workspace directory still exists. For Codex, read
setup status for repository or directory-trust failures. Confirm the ticket
worktree is not dirty, missing, or already used by another active run.

## Git work is conflicted

Open the Git sidebar and use the conflict resolver for supported text conflicts.
Use external git tooling for structural conflicts. Preserve the worktree and run
`git status` before attempting cleanup.

## Notifications are missing

Check operating-system notification permission. A denied or unavailable system
notification does not stop the run; use the in-app completion message as the
fallback.

## Still stuck?

Search the [issue tracker](https://github.com/brianofrokk3r/svdo-desktop/issues).
If the problem is new, follow the [bug report guide](../docs/creating-tickets.md)
and include version, install method, OS/version, architecture, exact steps, and
sanitized logs.

---

[← Settings and Integrations](Settings-and-Integrations.md) · [Wiki home](Home.md)
