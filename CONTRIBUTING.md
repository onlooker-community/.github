# Contributing to Onlooker Community

Thank you for contributing. This document covers how to contribute across all repositories in the `onlooker-community` organization.

---

## Before You Start

**For bug fixes and small improvements:** open a pull request directly. No issue required for changes under ~50 lines.

**For new features, new plugins, or new runtime adapters:** open an issue first and describe what you want to build. We want to make sure it fits before you invest significant time.

**For schema changes:** schema changes have the widest blast radius in the ecosystem. Open an issue tagged `schema-change` and expect a longer review process. Any change that could break existing events requires a migration plan before the PR will be reviewed.

---

## Repository-Specific Notes

### `marketplace` — adding or modifying a plugin

Every plugin must have a valid `manifest.json`. The schema lives at `.claude-plugin/schemas/manifest.v1.json`. CI validates all manifests on every PR — fix validation errors before requesting review.

New plugins go through a one-week comment period in the issue before a PR is opened. This gives the community time to raise concerns about scope, naming conflicts, or overlap with existing plugins.

Plugin names are lowercase, hyphenated, and must be unique across the marketplace. Check existing plugins before proposing a name.

**Platform-hosted features:** Some plugin capabilities — cross-session knowledge persistence, structured memory search, dashboard visualizations, weekly synthesis briefs — are delivered by the platform at `app.onlooker.dev` rather than local packages. Plugins write canonical `OnlookerEvent` entries through the schema; the platform indexes and surfaces them. If you're working on a plugin that needs persistent state across sessions (archivist, relay, scribe, counsel, cartographer), the plugin's job is to emit well-structured events — not to manage storage. See `schema/README.md` for the event types these plugins use.

### `schema` — changing the canonical event schema

The schema is the contract the entire ecosystem depends on. Changes follow this process:

1. Open an issue describing the change, why it's needed, and which repos will be affected
2. Label it `schema-change` — this flags it for review by maintainers in `onlooker`, `adapter-sdk`, and `meridian`
3. All additive changes (new optional fields, new event types) can go in a minor version
4. Any breaking change (removing fields, changing types, renaming event types) requires a major version bump
5. Major version bumps require a deprecation window: the old schema version continues to be supported for at least 60 days after the new one ships

### `onlooker` (daemon) — changing the Go binary

The daemon is the most widely installed component. Changes that affect config format, database schema, or sync protocol require extra scrutiny.

- Config format changes must be backwards compatible: old config files should continue to work
- Database schema changes must include a migration that runs automatically on startup
- Sync protocol changes must maintain compatibility with the current API server version

### `adapter-sdk` and adapters — changing the adapter interface

Adapter interface changes affect every runtime adapter. Adding optional methods to the interface is safe. Removing or changing method signatures requires a major version bump.

---

## Pull Request Process

1. **Branch naming:** `fix/short-description`, `feat/short-description`, `docs/short-description`, `chore/short-description`

2. **Commit messages:** use conventional commits — `fix:`, `feat:`, `docs:`, `chore:`, `refactor:`, `test:`. The release automation reads these to determine version bumps.

3. **Tests:** all PRs must pass existing tests. New features need new tests. The CI matrix covers what's required — don't ship green PRs with skipped tests.

4. **Changelog:** for user-visible changes, add an entry to `CHANGELOG.md` in the format the repo uses. If the repo uses automated changelog generation, this is done for you.

5. **One concern per PR:** split unrelated changes into separate PRs. A PR that fixes a bug and refactors unrelated code will be asked to split.

6. **Review:** PRs need at least one approval from a maintainer. For changes to `schema`, `adapter-sdk`, or the daemon's sync protocol, two maintainer approvals are required.

---

## Development Setup

Most TypeScript repos follow the same pattern:

```bash
git clone https://github.com/onlooker-community/<repo>
cd <repo>
npm install        # or bun install
npm run build
npm test
npm run typecheck
```

The daemon requires Go 1.23+:

```bash
git clone https://github.com/onlooker-community/onlooker
cd onlooker
go build ./cmd/onlooker
go test ./...
```

---

## Reporting Issues

Use the issue templates provided in each repository. They prompt for the information needed to triage efficiently — incomplete issue reports will be closed.

**Security vulnerabilities:** do not open a public issue. Follow the process in [SECURITY.md](./SECURITY.md).

---

## Becoming a Maintainer

Maintainers are contributors who have demonstrated sustained, high-quality contributions to a specific repo. If you're interested, contribute consistently for a few months and ask in the relevant repo's discussions.

Maintainers are expected to review PRs within 5 business days and to be reachable for security disclosures.
