# imb-shared-services/.github

Organization-wide defaults for every repository under `imb-shared-services`.

GitHub treats this repository specially: the community health files here
(`CONTRIBUTING.md`, `SECURITY.md`, `PULL_REQUEST_TEMPLATE.md`, issue templates)
apply to any repository in the organization that does not carry its own copy.
Workflow templates under `workflow-templates/` appear in every repository's
**Actions → New workflow** page.

| Path | Purpose |
| --- | --- |
| `CONTRIBUTING.md` | How changes are proposed, reviewed, and merged |
| `SECURITY.md` | Reporting vulnerabilities; secrets policy |
| `PULL_REQUEST_TEMPLATE.md` | Default PR body |
| `ISSUE_TEMPLATE/` | Bug report and task templates |
| `CODEOWNERS` | Review ownership for *this* repository (each repo carries its own) |
| `workflow-templates/` | Starter CI workflows offered to new repositories |
| `.github/workflows/` | CI for this repository (YAML and Markdown lint) |
| `.github/dependabot.yml` | Keeps the actions used here current |

## Visibility

This repository is **public by necessity**: GitHub only honours
organization defaults from a public `.github` repository. It therefore
contains policy and templates only — no configuration, hostnames,
identities, or anything specific to IMB or portfolio-company systems. Keep it that way.

## Ownership

The group finance team owns the content of this repository. Changes follow the
same rules as any other repository: branch, pull request, one approving
review, merge. Organization settings (membership, security policy, billing)
are administered by the organization owners and are not configured here.

## Scope

This organization holds the IMB portfolio's **shared-services finance
platform**: the reporting spine, close automation, and data marts that serve
the portfolio companies. Portfolio-company product code, client codebases,
and government codebases are never mirrored, forked, or referenced here;
they remain in their own environments under their own controls.

Deliberately omitted: `CODE_OF_CONDUCT.md` and `SUPPORT.md`. This is a
small internal team; the employee handbook governs conduct, and support is
a conversation, not a queue.
