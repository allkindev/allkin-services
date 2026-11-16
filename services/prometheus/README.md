# Prometheus

Metrics and PromQL queries, instant or over a range.

## Nothing to enter

Prometheus has no authentication of its own: the address is enough. If yours
sits behind a reverse proxy with a password, use the generic "any API with a
key" entry instead.

## Good to know

A range query can return a lot: the agent keeps ranges short and steps
coarse. The targets page tells which exporters are up.
