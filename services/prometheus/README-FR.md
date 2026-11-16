# Prometheus

Métriques et requêtes PromQL, instantanées ou sur une plage.

## Rien à saisir

Prometheus n'a pas d'authentification à lui : l'adresse suffit. Si le tien est
derrière un reverse proxy avec mot de passe, prends plutôt l'entrée générique
« n'importe quelle API à clé ».

## Bon à savoir

Une requête sur une plage peut rendre beaucoup : l'agent garde des plages
courtes et des pas larges. La page des cibles dit quels exporteurs répondent.
