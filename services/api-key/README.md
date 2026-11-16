# Other API-key service

The catch-all entry: any REST API authenticating with a constant key.

## What to fill in

**The base URL** — the API root, without a trailing slash. The paths the agent
gives will be appended to it:

```
https://api.example.com/v1
```

**Where to put the key** — three forms cover nearly every API:

| Placement | What it produces | Example |
| --- | --- | --- |
| Header | `Authorization: Bearer <key>` | most of them |
| Query | `?api_key=<key>` | weather, indexers |
| Path | the URL contains `{secret}` | Telegram |

The fine settings — header name, prefix, suffix — exist for unusual formats such
as `X-Emby-Token: <key>` or `Authorization: MediaBrowser Token="<key>"`.

## What actually helps

The **"Instructions for agents"** field. An agent meeting an unknown API has no
documentation: two lines about the useful endpoints save it half a dozen
exploratory calls — and save you too, since each one is billed.

## Good to know

If the API you are wiring up comes back often, it deserves its own catalogue
entry: a folder under `src/services/`, an `index.ts`, and this README. It will
then appear everywhere with its logo, its help and its safeguards.
