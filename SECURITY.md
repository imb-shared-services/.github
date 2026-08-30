# Security policy

## Reporting a vulnerability

Report suspected vulnerabilities in any `imb-shared-services` repository or
in the systems they deploy to <jbritt@ashburnconsulting.com> (group CFO). Do not
open a public issue. Include the repository, the affected component, steps
to reproduce, and any impact you have observed.

You will receive an acknowledgement within two business days and a
remediation plan or a decision within ten.

## Secrets

- No credential, token, key, connection string, or password is ever
  committed — not in code, configuration, tests, fixtures, or history.
- Push protection is enabled on every repository. A blocked push is a
  defect in the change; fix the change. Do not bypass the block.
- Secrets are held in the IMB 1Password vaults and, for tenant-side
  runtimes, in Azure Key Vault. Code references a secret by
  name and resolves it at run time; it never holds the value.
- If a secret does reach a repository: treat it as compromised, rotate it
  immediately, then remove it from history. Rotation comes first — history
  rewriting is not a substitute.

## Dependencies

Dependabot alerts are enabled organization-wide. Security updates are
reviewed and merged with the same priority as a production bug. Pin
dependencies; review a new dependency's provenance before adding it.

## Scope boundary

This organization contains the IMB shared-services finance platform only.
Portfolio-company products, client systems, and government systems — their
data and source code — are out of scope for this policy and out of bounds
for these repositories.
