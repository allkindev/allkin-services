# Grafana

Tableaux de bord, sources de données et leurs requêtes, alertes, annotations.

## Le jeton

**Administration → Users and access → Service accounts → Add service
account**, avec le rôle dont l'agent a besoin (Viewer pour lire), puis **Add
service account token**. L'adresse est celle de Grafana.

## Bon à savoir

Enregistrer un tableau de bord le remplace, et supprimer quoi que ce soit
demande ta confirmation. Interroger une source de données à travers Grafana
marche pour Prometheus, Loki et les sources SQL de la même façon.
