# SVDO Desktop

This repository is primarily the documentation and ticket-tracking home for
SVDO Desktop, a local Kanban board and agentic project runner. Application
source is maintained separately.

- [Read the usage wiki](wiki/Home.md)
- [Create a useful ticket](docs/creating-tickets.md)
- [Open the issue tracker](https://github.com/brianofrokk3r/svdo-desktop/issues)

## Install

On a supported macOS or Linux computer, use the recommended installer:

```sh
curl -fsSL https://packages.svdo.ai/install.sh | sh
svdo desktop
```

The installer chooses npm when available, then Bun. It installs the current
hosted production package.

### Anonymous installation telemetry

The installer sends anonymous, best-effort installation telemetry to help the
project understand system configurations needed for build compatibility. It
reports only:

- Operating system and CPU architecture.
- The production install channel.
- Whether installation completed and, when available, the installed version.
- A randomly generated installation identifier used to associate the start and
  completion events.

It does **not** report how you use SVDO or collect account details, workspace
paths or contents, tickets, prompts, agent activity, or credentials. Telemetry
failure never blocks installation. Disable it entirely by setting
`SVDO_TELEMETRY=0`:

```sh
curl -fsSL https://packages.svdo.ai/install.sh | SVDO_TELEMETRY=0 sh
```

You can install the same package directly when Node.js 24+ and npm are already
available:

```sh
npm install -g https://packages.svdo.ai/desktop-local/production/current.tgz
```

Or install it with Bun:

```sh
bun add -g https://packages.svdo.ai/desktop-local/production/current.tgz
```

Homebrew is not currently a documented public install path because no public tap
has been named. Do not install the unrelated `joule` package from the public npm
registry.

## Compatibility

| Item | Requirement |
| --- | --- |
| Shell installer | macOS or Linux |
| CPU for shell installer | 64-bit Intel/AMD (`x86_64`/`amd64`) or ARM (`arm64`/`aarch64`) |
| npm installation | Node.js 24 or newer |
| Bun installation | A current Bun installation capable of global package installs |
| Windows | Release packages are built on Windows, but the shell installer does not run there; use the npm package path with Node.js 24+ |
| Local tools | Git and at least one configured agent CLI are needed for their corresponding workflows |

No minimum macOS, Linux distribution, or Windows version is currently stated by
the application source. If your system falls outside the combinations above,
[open a compatibility ticket](docs/creating-tickets.md) with full environment
details.

After installation, run `svdo --help` to verify the CLI. If it is not found,
open a new terminal or add your package manager's global binary directory to
`PATH`. Continue with [Getting Started](wiki/Getting-Started.md).

## Desktop commands

Launch Desktop, then initialize projects from their repository directories:

```sh
svdo desktop
cd /path/to/project
svdo init
```

The Desktop runtime normally chooses an available local port. To require a
specific port for this launch, set `PORT`:

```sh
PORT=4101 svdo desktop
```

Other useful commands in a Desktop workflow are:

```sh
svdo init [path]                         # register a workspace
svdo status [path]                       # show its assigned tickets
svdo backup --destination /path/copy.db  # back up the local database
svdo version                             # show the installed version
svdo --help                              # show CLI help
```

See [Getting Started](wiki/Getting-Started.md) for launch and port details,
[Tickets and Agent Runs](wiki/Tickets-and-Agent-Runs.md) for run workflows, and
[Settings and Integrations](wiki/Settings-and-Integrations.md) for Agents and
Skills.

## Get help or propose a change

Search existing tickets before opening a new one. Include enough context for
someone else to reproduce a problem or understand the desired outcome; never
post credentials or other secrets. The [ticket creation guide](docs/creating-tickets.md)
contains bug and feature-request checklists.

General how-to material belongs in the [usage wiki](wiki/Home.md), keeping this
README focused on installation and compatibility.
