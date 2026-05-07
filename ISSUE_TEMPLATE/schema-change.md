---
name: Schema change proposal
about: Propose a change to the canonical event schema
labels: schema-change
---

<!-- 
  Schema changes have the widest blast radius in the ecosystem.
  Every consumer of @onlooker-community/schema — the daemon, all adapters,
  all plugins that write events — is affected.
  
  Read the schema change section in CONTRIBUTING.md before proceeding.
-->

## What change is needed

<!-- Describe the change precisely. New field? New event type? Changed type? Removed field? -->

## Why is this needed

<!-- What use case does this enable that the current schema doesn't support? -->

## Is this additive or breaking?

- [ ] **Additive** — adds new optional fields or new event types (minor version bump)
- [ ] **Breaking** — removes fields, changes types, renames event types (major version bump + deprecation window)

## Affected consumers

<!-- Which repos and packages will need to be updated? -->

- [ ] `onlooker` daemon (normalizer)
- [ ] `adapter-sdk` (base types)
- [ ] `adapter-claude-code`
- [ ] `adapter-cursor`
- [ ] Marketplace plugins (list which):
- [ ] Meridian
- [ ] `app` (sync API, platform dashboard, knowledge graph)
- [ ] Meridian

## Migration plan (for breaking changes)

<!-- 
  How will existing consumers be migrated?
  What is the proposed deprecation timeline?
  How will the daemon handle events from both the old and new schema version simultaneously?
-->

## Proposed schema diff

```json
// Before
{
  ...
}

// After
{
  ...
}
```
