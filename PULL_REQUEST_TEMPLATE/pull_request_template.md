## What this PR does

<!-- One paragraph. Be specific about what changed and why. -->

## Type of change

- [ ] Bug fix (non-breaking)
- [ ] New feature (non-breaking)
- [ ] Breaking change (requires version bump and migration notes)
- [ ] Schema change (requires review by schema maintainers)
- [ ] Documentation
- [ ] Chore / dependency update

## Testing

<!-- How did you verify this works? What tests did you add or update? -->

- [ ] Existing tests pass (`npm test` / `go test ./...`)
- [ ] New tests added for new behavior
- [ ] Manually tested against:

## For schema changes

- [ ] `schema_version` field updated in affected event types
- [ ] Migration notes added to CHANGELOG.md
- [ ] Breaking changes flagged and deprecation timeline proposed

## For new or changed plugins

- [ ] `manifest.json` version bumped
- [ ] `manifest.json` validates against the schema (`npx ajv-cli validate ...`)
- [ ] README updated

## Checklist

- [ ] Conventional commit message (`fix:`, `feat:`, `docs:`, etc.)
- [ ] CHANGELOG.md entry added (for user-visible changes)
- [ ] No unintended dist/ or generated file changes

## Related issues

<!-- Closes #, Fixes #, or "No related issue" -->
