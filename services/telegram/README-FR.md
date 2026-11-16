# Telegram

Un canal de sortie : l'agent envoie des messages, il n'en reçoit aucun.

## Créer le bot

Écris à **@BotFather** sur Telegram, commande `/newbot`. Il te rend un jeton de
la forme `123456789:AAE...`.

## L'identifiant de conversation

C'est le champ le plus important, et le seul qui demande une manipulation.

1. Envoie un message à ton bot (ou ajoute-le à un groupe et écris-y).
2. Ouvre `https://api.telegram.org/bot<TON_JETON>/getUpdates`.
3. Relève `chat.id` — **négatif** pour un groupe, positif pour une conversation
   directe.

## Pourquoi ce champ est imposé

Une clé de bot Telegram peut écrire à **n'importe quelle** conversation que le
bot connaît. L'identifiant que tu saisis ici est réécrit par Allkin dans chaque
appel, en écrasant ce que l'agent aurait mis.

Autrement dit : ce n'est pas une consigne, c'est une contrainte. Le bot ne
pourra écrire qu'à cette conversation, quoi qu'un agent demande.

## Bon à savoir

Le bouton « Envoyer un message d'essai » de la fiche du service envoie un vrai
message. C'est le seul moyen de vérifier la destination — une clé valide ne
prouve pas que le message arrive au bon endroit.
