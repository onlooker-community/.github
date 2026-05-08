# Onlooker Community

Observability and intelligence infrastructure for AI-assisted development.

---

## What We Build

**[Onlooker](https://github.com/onlooker-community/onlooker)** — the background daemon that watches your AI development sessions, buffers telemetry locally, and syncs to your account. The spine of the ecosystem.

**[Marketplace](https://github.com/onlooker-community/marketplace)** — the official plugin marketplace. Safety gates, quality judges, session memory, cost tracking, regression testing, and more. Currently Claude Code native, expanding to all major runtimes.

**[Meridian](https://github.com/onlooker-community/meridian)** — the intelligence layer. Waypoint recovers learning signal from agent failures. Scout makes session context visible and manipulable. Beacon monitors production agents. The Playbook accumulates organizational knowledge from both.

**[Schema](https://github.com/onlooker-community/schema)** — the canonical event schema. The contract between runtimes, plugins, and the daemon.

---

## Getting Started

```bash
# Install the daemon
brew install onlooker-community/tap/onlooker

# Link to your account
onlooker link

# Start watching
onlooker daemon
```

Then install plugins from the marketplace in Claude Code:

```bash
/plugin marketplace add onlooker-community/marketplace
/plugin install onlooker@onlooker-marketplace
/plugin install sentinel@onlooker-marketplace
/plugin install tribunal@onlooker-marketplace
```

Full documentation at [docs.onlooker.dev](https://docs.onlooker.dev).

---

## Repositories

| Repo | Description |
|------|-------------|
| [onlooker](https://github.com/onlooker-community/onlooker) | Background daemon — telemetry collection and sync |
| [website](https://github.com/onlooker-community/website) | The website at onlooker.dev |
| [marketplace](https://github.com/onlooker-community/marketplace) | Official plugin marketplace |
| [meridian](https://github.com/onlooker-community/meridian) | Agent intelligence suite — Waypoint, Scout, Beacon |
| [schema](https://github.com/onlooker-community/schema) | Canonical event schema |
| [adapter-sdk](https://github.com/onlooker-community/adapter-sdk) | Runtime adapter interface and utilities |
| [adapter-claude-code](https://github.com/onlooker-community/adapter-claude-code) | Claude Code runtime adapter |
| [adapter-cursor](https://github.com/onlooker-community/adapter-cursor) | Cursor runtime adapter |
| [app](https://app.onlooker.dev) | Web platform — app.onlooker.dev |
| [docs](https://github.com/onlooker-community/docs) | Documentation — docs.onlooker.dev |
| [homebrew-tap](https://github.com/onlooker-community/homebrew-tap) | Homebrew tap for binary distribution |

---

## Contributing

Read [CONTRIBUTING.md](https://github.com/onlooker-community/.github/blob/main/CONTRIBUTING.md) before opening a pull request.

All contributors must follow our [Code of Conduct](https://github.com/onlooker-community/.github/blob/main/CODE_OF_CONDUCT.md).

Security vulnerabilities: see [SECURITY.md](https://github.com/onlooker-community/.github/blob/main/SECURITY.md).

---

## License

All repositories under this organization are licensed under the [Blue Oak Model License 1.0.0](https://blueoakcouncil.org/license/1.0.0) unless otherwise noted.
