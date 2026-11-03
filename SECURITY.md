# Security

If you think you found a security problem in inkan or in one of the `@inkanjs` packages,
please don't open a public issue. Report it privately instead, so it can be fixed before
anyone can use it.

## How to report

Use GitHub's private reporting: open the repository the problem is in, go to
**Security → Report a vulnerability**, and describe what you found. Only the maintainer can
read it.

It helps a lot if you include:

- the package and version (`@vxnsin/inkan@0.8.1`, `@inkanjs/auth@0.2.0`, …)
- what an attacker can do, and what they need for it
- the smallest code or request that shows it
- whether it is already public somewhere

## What happens next

You'll get an answer within a week, usually sooner. Once the problem is confirmed, the fix
goes into a patch release, and the release notes say what was fixed and credit you, unless
you'd rather not be named. Please give it a reasonable time before you talk about it in
public; if a fix takes longer than 90 days, we'll agree on a date together.

## Supported versions

Security fixes go into the latest minor release of each package. inkan is before 1.0, so
older minors don't get backports; upgrading within the same major is meant to be easy (see
[the stability policy](https://inkan-dev.vercel.app/docs/stability)).

| package | supported |
| --- | --- |
| `@vxnsin/inkan` | 0.8.x |
| `@inkanjs/*` middleware | the latest release of each |
| `@inkanjs/*` integrations | the latest release of each |

## What counts

Anything that lets someone get around a check inkan promises to do: input getting past its
contract, an answer leaking a field its contract doesn't list, credentials, sessions or
tokens being forged or reused, cross-origin WebSocket use, injection through the stores,
a request that can take the server down far out of proportion to its size. If you're not
sure, report it anyway.
