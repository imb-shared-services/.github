# Contributing

Status: **draft v0.1** — maintained by the group finance team. Propose changes
to this document the same way as any other change: open a pull request.

These rules apply to every repository in the `imb-shared-services`
organization unless a repository's own `CONTRIBUTING.md` says otherwise.

## Ground rules

1. **`main` is always releasable.** Nothing reaches it except through a
   pull request with a passing CI run and one approving review from someone
   who did not author the change. This is enforced by branch protection and
   applies to administrators.
2. **No secrets in the repository, ever.** Push protection blocks known
   credential patterns; a block means the change is wrong, not that the
   scanner is. Secrets live in the IMB 1Password vaults (operator) or Azure
   Key Vault (tenant) and are referenced, never embedded. See `SECURITY.md`.
3. **Portfolio-company and client code stays out.** This organization is
   the shared finance platform only. Do not mirror, vendor, or paste code
   from a portfolio company's product, client, or government codebase into
   any repository here. Portfolio data reaches this platform only through
   the sanctioned read-only source pulls.
4. **Every script is safe to run twice.** Idempotent by default; a re-run
   must not duplicate, double-post, or destroy.

## Workflow

### Branches

Branch from `main`. Name branches `type/short-description`:

| Prefix | Use |
| --- | --- |
| `feat/` | New capability |
| `fix/` | Bug fix |
| `docs/` | Documentation only |
| `chore/` | Tooling, dependencies, housekeeping |
| `refactor/` | Behaviour-preserving restructuring |

Keep branches short-lived. Delete them after merge (the merge button does
this by default).

### Commits

One logical change per commit. Subject line in the imperative, ≤ 72
characters, prefixed with the same type as the branch:

```text
fix: guard numeric cast on empty timesheet rows
```

Use the body to explain **why** when it is not obvious from the diff.
Commits are authored under your work identity, never a personal one.

### Pull requests

- Fill in the template. A reviewer should understand the change, why it is
  needed, and how it was verified without opening the diff.
- Keep PRs reviewable: prefer several small PRs over one large one.
- CI must pass. A red check is the author's to fix, not the reviewer's.
- Resolve every review conversation before merge — either with a change or
  an agreed reason not to.
- The author does not approve their own PR. Owners cannot bypass this.
- Merge with **squash** unless the branch history is deliberately curated;
  the squashed commit message follows the commit rules above.

### Reviews

Review for correctness first, then clarity, then style. Ask for the test
that proves the fix. Approve when you would be comfortable being paged for
the change. Prefer a question to an assertion when unsure.

## Code expectations

- **Python 3.12+** is the default language. Other languages by agreement.
- **Tests:** unit tests for calculation and transformation logic; end-to-end
  smoke tests against a fixture for pipelines and integrations. New
  behaviour arrives with the test that exercises it.
- **Lint and format:** `ruff` (lint + format) for Python, `yamllint` for
  YAML, `markdownlint-cli2` for Markdown. Configuration lives in the
  repository; CI runs the same commands you run locally.
- **Dependencies:** minimal, pinned, and reviewed. Prefer the standard
  library. A new top-level dependency needs a one-line reason in the PR.
- **Configuration** is externalized (JSON/YAML/environment), never
  hard-coded. Repository-relative paths in code.
- **Output contract for scripts:** `stdout` carries structured, parseable
  status; `stderr` carries human-readable logs and errors.

## Getting access

Access is granted through organization teams, never per-repository to an
individual. Ask an organization owner to add you to the appropriate team.
Two-factor authentication is required for membership.
