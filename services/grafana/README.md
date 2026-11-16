# Grafana

Dashboards, data sources and their queries, alerts, annotations.

## The token

**Administration → Users and access → Service accounts → Add service
account**, with the role the agent needs (Viewer to read), then **Add service
account token**. The address is the one of Grafana.

## Good to know

Saving a dashboard replaces it and deleting anything ask for your
confirmation. Querying a data source through Grafana works for Prometheus,
Loki and the SQL sources alike.
