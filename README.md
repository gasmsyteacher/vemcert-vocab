# cachet-vocab

Published vocabulary for [Cachet](https://github.com/gasmsyteacher) verifiable credentials.

Served via GitHub Pages as the redirect target of the permanent identifier
`https://w3id.org/cachet/v1#`.

| File | Purpose |
|---|---|
| `v1.jsonld` | JSON-LD context (`Accept: application/ld+json`) |
| `v1.html` | Human-readable term reference (`Accept: text/html`) |
| `index.html` | Version index |

## This repository is a publishing target, not a source of truth

`v1.jsonld` is a **copy**. The authoritative definition lives in the Cachet
platform repository at `docs/vocab/v1.jsonld`, next to the code that embeds
these terms into signed credentials.

Nothing fetches these files at runtime. Credentials carry their term definitions
inline, so issuance, verification and JSON-LD expansion all work with no network
access — which is what makes a Cachet credential verifiable offline, from a
printed QR code, after the issuer's servers are gone. These files exist so the
IRI resolves for humans and for tools that follow it.

Consequence: **this copy can drift from what credentials actually carry, and
nothing will break until someone tries to interpret a credential.** A CI check in
the platform repository asserts that the two stay identical.

## Stability

`v1` is immutable. Terms may be added. A term's meaning is never changed and a
term is never removed — term IRIs are signed into credentials meant to verify
indefinitely. Breaking changes mint `/v2`.

## Setup

Enable GitHub Pages on the `main` branch, root directory. The permanent
identifier redirect lives in
[`perma-id/w3id.org`](https://github.com/perma-id/w3id.org) under `/cachet/`.

Note: GitHub Pages may not serve `.jsonld` as `application/ld+json`. This is
cosmetic here, since nothing dereferences the context at runtime, but verify the
`Content-Type` after deploying if an external consumer ever needs to fetch it.

## Maintainer

gasmsyteacher · <mail@virtualmindshub.com>
