# YouTube

Ta chaîne : vidéos, playlists, commentaires, abonnements, recherche.

## L'application

La même application Google Cloud que les autres services Google d'Allkin : **<https://console.cloud.google.com>** → un projet → **API et services → Identifiants → Créer des identifiants → ID client OAuth**, type **Application Web**, avec l'URI de redirection affichée dans l'onglet « Service » recopiée caractère pour caractère. Saisis ici son ID client et son secret, coche les portées, **Se connecter**.

Active **YouTube Data API v3** dans la **Bibliothèque** du même projet : une portée sur une API désactivée donne un refus qui ne dit pas pourquoi.

Tant que l'écran de consentement est en *Test*, seuls les utilisateurs de test peuvent autoriser et le jeton meurt au bout de sept jours : passe-le en *Production* pour une connexion durable. Voir l'aide de « Google (toutes API) » pour le détail.

## Bon à savoir

Le quota quotidien est de 10 000 unités et une recherche en coûte 100 : l'agent a pour consigne de chercher avec parcimonie. Modifier une vidéo et supprimer demandent ta confirmation. Les envois ne sont pas proposés par ce relais.
