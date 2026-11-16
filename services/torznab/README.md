# Torznab

The indexer query standard — Prowlarr, Jackett, and most trackers that expose a
search API.

## The base URL

This is the **exact API address**, not the site's domain name. A Torznab API has
no path: everything happens in the query parameters, and the address you give is
called as-is.

```
https://mysite.org/api           ✅
https://mysite.org               ❌ you will get the site's home page
```

The test checks this: it sends `?t=caps` — the one request the standard requires
of every indexer — and rejects a response that is not Torznab. A web page no
longer passes for an API.

Where to find the address:

- **Public indexer**: your profile page, alongside the key.
- **Prowlarr**: "Copy Torznab Url" button on the indexer; key under
  Settings → General.
- **Jackett**: "Copy Torznab Feed" button; key at the top of the dashboard.

It often ends in `/api`, sometimes in something like
`/api/v2.0/indexers/…/results/torznab`.

## What the agent does with it

It always starts with `?t=caps`, which tells it which searches and categories
the indexer accepts — this varies from one to another. Then `?t=search&q=…`,
`?t=tvsearch`, `?t=movie`.

The indexer answers in XML; **Allkin converts it to JSON** before handing it to
the agent. This is not for comfort: it is what lets the agent extract only what
it wants. A twenty-five-result search weighs over 20,000 characters, and
whatever enters a conversation is paid for again on every later turn. Asked for
titles alone, the same search comes back at 1,200.

Each result carries a download link the agent saves straight into its files, as
a `.torrent`.

## Your key does not reach the context

Many indexers repeat the key in clear text in **every** result's download link.
A single search would drop it dozens of times into the agent's conversation,
where it would stay.

Allkin replaces it before the response reaches the model. Measured on a real
search: twenty-five occurrences masked, zero in clear.
