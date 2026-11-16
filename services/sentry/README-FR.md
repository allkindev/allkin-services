# Sentry

Les erreurs de tes applications : issues, leurs événements et traces, versions, statistiques.

## Le jeton

**Settings → Auth Tokens → Create New Token** (un jeton d'organisation, limité à ce dont l'agent a besoin : `event:read`, `project:read`, `event:write` pour résoudre). L'adresse est `https://sentry.io`, ou la racine de ton Sentry auto-hébergé.

## Bon à savoir

Un événement avec sa trace est volumineux : l'agent lit d'abord la liste des issues. Supprimer demande ta confirmation.
