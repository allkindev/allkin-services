# Gmail

Ta boîte Gmail : lire, chercher, étiqueter, répondre et envoyer.

## L'application

La même application Google Cloud que les autres services Google d'Allkin : **<https://console.cloud.google.com>** → un projet → **API et services → Identifiants → Créer des identifiants → ID client OAuth**, type **Application Web**, avec l'URI de redirection affichée dans l'onglet « Service » recopiée caractère pour caractère. Saisis ici son ID client et son secret, coche les portées, **Se connecter**.

Active **Gmail API** dans la **Bibliothèque** du même projet : une portée sur une API désactivée donne un refus qui ne dit pas pourquoi.

Tant que l'écran de consentement est en *Test*, seuls les utilisateurs de test peuvent autoriser et le jeton meurt au bout de sept jours : passe-le en *Production* pour une connexion durable. Voir l'aide de « Google (toutes API) » pour le détail.

## Bon à savoir

« Lire les mails » suffit pour un agent qui ne fait que lire ; « Envoyer » seulement s'il doit écrire. L'envoi demande ta confirmation.
