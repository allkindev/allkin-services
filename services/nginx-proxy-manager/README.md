# Nginx Proxy Manager

Gives an agent control over your reverse proxy: list published domains, see
which service each one serves, diagnose a configuration that won't load,
publish a new service, request a certificate.

## What you need

Two things, both from Nginx Proxy Manager itself:

| Field | Where to find it |
| --- | --- |
| Base URL | The admin interface address, **followed by `/api`** |
| Email address, password | The ones you use to sign in to that interface |

## The base URL

This is the one thing people get wrong. The address must point at the API, not
at the page:

```
http://127.0.0.1:81/api      ✅
http://127.0.0.1:81          ❌ "405 Not Allowed", a web page instead of the API
```

Port **81** is the admin interface — not to be confused with ports 80 and 443,
which carry the traffic of the sites the proxy serves. If Nginx Proxy Manager
runs on another machine, replace `127.0.0.1` with its address.

## Which account to use

The one from the web interface. Two notes:

- **Two-factor authentication blocks this connection.** An identity/password
  exchange cannot get past it: the service replies that it expects a second
  factor, and Allkin will tell you so. Use an account without it enabled.
- **The account's email address is also used by Let's Encrypt.** It is what
  gets sent to the certificate authority on a request — there is no separate
  field for it.

You can create a dedicated account for Allkin (Users → Add User) rather than
handing over your own: permissions are per-user, and read-only access is enough
for an agent that only needs to monitor.

## What the agent can do, and what you approve

Reading asks nothing: list hosts, certificates, access lists, audit log,
reports, diagnose a failing configuration.

Anything that changes what the internet sees of the machine goes through your
approval, in the conversation:

| What the agent asks for | Why it needs approval |
| --- | --- |
| Publish or modify a host | A domain becomes reachable, or starts pointing elsewhere |
| Disable a host | The domain stops responding |
| Delete an entry | The configuration is erased, not disabled: it has to be rebuilt |
| Request a certificate | Let's Encrypt allows 5 identical certificates per week |
| Delete a certificate | Every host using it loses HTTPS |
| Open a TCP/UDP stream | A port is forwarded as-is, with no domain and no encryption |
| Touch accounts or settings | A changed password can lock you out |

Re-enabling a host, on the other hand, asks nothing: what breaks gets approved,
what repairs does not.

This is not an instruction given to the agent: the code intercepts the call. An
agent cannot opt out of it.

If you want to go further, the **"Read-only on services"** box in the agent's
permissions closes all writing at once — the tool then only carries methods
that change nothing.

## Password and session

The password is used once, to obtain a token. It is that token — dated by Nginx
Proxy Manager, renewed automatically when it expires — that travels afterwards.
The agent sees neither.

## If something goes wrong

| What you read | What it means |
| --- | --- |
| "connection refused" on the test | Email or password. The service replies `Invalid email or password` |
| "the response is a web page" | `/api` is missing from the end of the base URL |
| "no `token` field came back" | The account uses two-factor authentication |
| "Connection refused: nothing is listening" | Wrong port — admin is on 81, not 80 |
