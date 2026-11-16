# Grafana

Dashboards, Datenquellen und ihre Abfragen, Alarme, Anmerkungen.

## Das Token

**Administration → Users and access → Service accounts → Add service
account**, mit der Rolle, die der Agent braucht (Viewer zum Lesen), dann **Add
service account token**. Die Adresse ist die von Grafana.

## Gut zu wissen

Das Speichern eines Dashboards ersetzt es, und jedes Löschen fragt nach deiner
Bestätigung. Eine Datenquelle über Grafana abzufragen funktioniert für
Prometheus, Loki und die SQL-Quellen gleichermaßen.
