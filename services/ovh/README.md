# OVHcloud — service account

Domains, hosting, dedicated servers, VPS, Public Cloud: the OVHcloud API exposes
just about everything the manager can do.

> **Service account, not an API key.** These are two different mechanisms at
> OVH, and the confusion is the most common failure. The `api.ovh.com/createToken`
> page that every tutorial points to yields **three** values and belongs to the
> other catalogue entry, "OVHcloud (API keys)". A service account yields **two**.

## Creating the service account

Manager → **Identity, security and operations** → **Identities** → **Service
account** → "Add a service account".

- The **name you choose is the client ID**.
- The **password shown is the secret**, displayed once.

## The step people miss, which leaves the agent blind

A brand-new service account starts with **no resources at all**. The connection
succeeds, the agent queries the API, and gets empty lists — not a refusal, an
`HTTP 200` with zero results. Nothing signals that something is missing: it
looks like an empty account.

You must grant it rights under **Policies** (same section of the manager):
create a policy, pick the resources, attach the service account to it.

Many people stop here, because that interface is temperamental. If you cannot
get through it, take the other route: **"OVHcloud (API keys)"** in the
catalogue, whose rights are ticked at key-creation time.

## What the agent does not do alone

Twenty-eight call patterns go through your approval — buying and paying for an
order, terminating a service, deleting a DNS zone, reinstalling a server. The
agent can prepare them and submit them to you; it cannot trigger them.

Everything else — reading the catalogue, listing your products, filling a cart —
goes through without asking.

## Good to know

- Defaults target **Europe** (`eu.api.ovh.com`). Canadian and US accounts have
  their own API root.
- Account information (`/me`) is denied to a service account by default, while
  products stay reachable. A `403` on `/me` is therefore not a sign of a broken
  setup.
