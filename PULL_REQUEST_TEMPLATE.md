## What

<!-- One or two sentences. What does this change do? -->

## Why

<!-- The problem or need. Link the issue if there is one: Closes #NNN -->

## How it was verified

<!-- Commands run, tests added, fixture used, manual check performed. -->

## Risk and rollback

<!-- What could this break? How is it undone — revert, config flag, redeploy? -->

## Checklist

- [ ] CI is green
- [ ] Tests cover the new or changed behaviour
- [ ] No secrets, credentials, or client data in the diff
- [ ] Documentation updated where behaviour changed
- [ ] Safe to run twice (scripts and migrations are idempotent)
