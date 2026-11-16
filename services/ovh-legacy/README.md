# OVHcloud — API keys

OVH's legacy method: three keys and a per-request signature.

**This is the route to take if you want the agent to be able to order.**
Verified on a real account: these keys bypass IAM where a service account runs
into it. They act under the account's own identity, with the ADMIN role, rather
than under a fresh identity with no rights.

## Creating the keys

Open **<https://api.ovh.com/createToken/>**, signed in to your account.

| Field | Value |
| --- | --- |
| Script name | `allkin` |
| Validity | Unlimited |
| Rights | the useful minimum |

On rights: `GET` on `/*` is enough for an agent that reads. Only add `POST`,
`PUT` and `DELETE` on `/*` if the agent must write — **those rights apply to
your whole account**, with no distinction between products.

The page then returns **three values**, to be entered in the three fields of the
"Service" tab. They are shown only once.

## The trade-off

No IAM policy to create: the rights you tick are effective from the first
request. That is the whole point of this route.

In exchange, these keys are broad. What bounds the agent here is not OVH: it is
Allkin, which intercepts purchase, payment, termination and deletion and submits
them to you. Still, narrow the patterns rather than ticking everything — a
safeguard is better when it is not the only one.

## Good to know

The signature is computed by Allkin on every call, over the method, URL and
body. The application secret never leaves the machine: it only feeds the hash.
