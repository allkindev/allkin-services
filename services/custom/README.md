# Other OAuth2 service

The catch-all entry for a service authenticating through OAuth2 without being in
the catalogue.

## What to fill in

- **Authorisation URL** and **token URL** — the service's two OAuth2 endpoints,
  from its documentation.
- **Client ID** and **client secret** — obtained by registering an application
  with it.
- **Scopes** — space-separated.

## The redirect URI

The address shown on the "Service" tab must be copied **exactly** into the
application's configuration on the provider's side. This is the near-universal
cause of connection refusals: a different port, one trailing slash too many, and
the authorisation is rejected.

## Good to know

This entry assumes the "on behalf of a user" flow: a "Connect" button, a
redirect, a return. A service that authenticates itself — service account,
`client_credentials` — is not configured here; it needs its own catalogue entry,
like OVHcloud.
