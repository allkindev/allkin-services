# Hacker News

Stories and comments through the official API, search through Algolia.

## Nothing to enter

No key on either side. The test reads the id of the latest item.

## Good to know

The official API only lists ids: reading a front page means one call per
story, which is why the agent is told to stop at the first dozens. Searching,
filtering by date or score goes through `hn.algolia.com`, reachable through
this service.
