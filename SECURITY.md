# Security Policy

Last edited: 2026-07-16 13:15:15 GMT+8

OpenSatia is local-first software that may eventually interact with provider
accounts, browser sessions, personal food history, and cart state. Reports
that cross an authority, privacy, approval, or side-effect boundary should be
handled privately first.

## Supported Versions

OpenSatia is pre-release. Security fixes apply to the current `main` branch;
older commits and experimental forks are not supported releases.

## Report Privately

Use [GitHub private vulnerability reporting](https://github.com/OpenSatia/opensatia/security/advisories/new).
Do not open a public issue for a vulnerability, credential exposure, private
provider detail, payment hazard, or duplicate-order risk.

Include what you can safely provide:

- affected component and commit
- severity and user impact
- minimal reproduction steps
- whether a provider cart, account, payment, or private record was affected
- sanitized logs or screenshots when necessary
- suggested mitigation, if known

Never include live credentials, cookies, payment details, full addresses, or
another person's data. Maintainers may ask for a narrower private reproduction.

## Security And Safety Boundaries

The first public version must not:

- place an order, submit payment, or click final confirmation
- reuse an approval for a different or stale provider action
- add duplicate cart lines through retries
- clear existing, user-saved, or unknown cart items
- expose browser credentials or authenticated captures to the Gateway, logs,
  repository, or model provider
- present inferred allergens, ingredients, nutrition, prices, or availability
  as provider-confirmed facts

Allergen uncertainty is also a product-safety concern. When a report contains
private user or provider evidence, use the private channel above. A sanitized
reproduction that contains no sensitive data may be filed as a public bug.

## Usually Not A Vulnerability

The following are normally reliability or product-quality reports unless they
also cross a security or authority boundary:

- a recommendation that is unappealing but respects hard constraints
- provider UI drift that stops safely before mutation
- stale availability that is clearly labeled and revalidated before handoff
- disagreement between nutrition estimates that remains honestly labeled

When uncertain, report privately. Maintainers can reroute the issue without
forcing sensitive details into public history.

## Disclosure

Please allow maintainers reasonable time to reproduce, contain, and publish a
fix before public disclosure. OpenSatia will credit responsible reporters when
requested and when doing so does not create additional risk.
