# Microsoft 365

Ton compte Microsoft par Graph : mail et agenda Outlook, OneDrive, To Do, contacts.

## L'application

Une application enregistrée dans Entra ID : **<https://entra.microsoft.com>** → **Inscriptions d'applications → Nouvelle inscription**, type de compte *personnels et professionnels*, URI de redirection de type **Web** réglée sur l'adresse qu'Allkin affiche sur cette page. Puis **Certificats et secrets → Nouveau secret client** (copie sa *valeur*, pas son identifiant). Saisis l'ID d'application (client) et le secret, coche les portées dont l'agent a besoin, et **Se connecter** : Microsoft te demande d'autoriser.

## Bon à savoir

Garde *Rester connecté* coché, sinon la connexion meurt au bout d'une heure. Envoyer un mail et supprimer demandent ta confirmation. Un 403 veut dire qu'une portée n'a pas été accordée : reconnecte-toi avec.
