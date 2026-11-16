# Google Docs

Documents : lire leur contenu, les créer, écrire et mettre en forme.

## L'application

La même application Google Cloud que les autres services Google d'Allkin : **<https://console.cloud.google.com>** → un projet → **API et services → Identifiants → Créer des identifiants → ID client OAuth**, type **Application Web**, avec l'URI de redirection affichée dans l'onglet « Service » recopiée caractère pour caractère. Saisis ici son ID client et son secret, coche les portées, **Se connecter**.

Active **Google Docs API** dans la **Bibliothèque** du même projet : une portée sur une API désactivée donne un refus qui ne dit pas pourquoi.

Tant que l'écran de consentement est en *Test*, seuls les utilisateurs de test peuvent autoriser et le jeton meurt au bout de sept jours : passe-le en *Production* pour une connexion durable. Voir l'aide de « Google (toutes API) » pour le détail.

## Bon à savoir

Le test de connexion ne peut pas appeler Docs sans document : le jeton est vérifié à « Se connecter ». Trouver un document est le travail de Google Drive : donne les deux à l'agent s'il doit chercher.
