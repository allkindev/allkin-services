# Google

Gmail, Agenda, Drive, Sheets — par OAuth2, au nom de ton compte.

## Créer les identifiants

**<https://console.cloud.google.com>** → un projet → **API et services** →
**Identifiants** → **Créer des identifiants** → **ID client OAuth** →
type **Application Web**.

## L'URI de redirection

C'est l'erreur numéro un (`redirect_uri_mismatch`). L'adresse affichée dans
l'onglet « Service » doit être recopiée **à l'identique** dans « URI de
redirection autorisés », caractère pour caractère : le protocole, le port et
l'absence de barre finale comptent.

Si tu ouvres Allkin sous plusieurs adresses (nom de domaine, adresse IP,
`localhost`), déclare-les toutes : Google compare avec celle par laquelle tu
arrives, pas avec une préférée.

## Activer les API

Chaque service Google est une API distincte, à activer séparément dans
**Bibliothèque** : Gmail API, Google Calendar API, Google Drive API, Google
Sheets API. Une portée accordée sur une API désactivée donne un refus qui ne dit
pas pourquoi.

## Les portées

Coche seulement ce dont l'agent a besoin. `gmail.readonly` suffit à lire une
boîte ; ne donne l'écriture que si l'agent doit vraiment envoyer.

Modifier les portées d'un service déjà connecté périme son jeton : il faudra
refaire « Se connecter ».

## Écran de consentement

Tant que l'application est en mode **Test**, seuls les comptes ajoutés comme
« utilisateurs de test » peuvent l'autoriser, et le jeton de rafraîchissement
expire au bout de sept jours. Passe l'application en **Production** si tu veux
une connexion durable.
