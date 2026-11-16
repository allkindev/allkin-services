# Zoom

Réunions, enregistrements, utilisateurs et rapports de ton compte Zoom.

## L'application

Une application **Server-to-Server OAuth** : **<https://marketplace.zoom.us>** → **Develop → Build App → Server-to-Server OAuth**. Sa page *App Credentials* donne trois valeurs : **Account ID**, **Client ID**, **Client Secret**. Ajoute les portées dont l'agent a besoin (meeting:read:admin, meeting:write:admin, recording:read:admin…) et active l'application. Saisis les trois valeurs ; *Tester* obtient un jeton.

## Bon à savoir

Le jeton vit une heure et Allkin le renouvelle. Annuler une réunion ou supprimer un enregistrement demande ta confirmation.
