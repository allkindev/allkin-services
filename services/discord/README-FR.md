# Discord

Serveurs, salons et messages, par un bot à toi.

## Le bot

**<https://discord.com/developers/applications>** → **New Application → Bot → Reset Token** : le jeton. Dans *Privileged Gateway Intents*, active **Message Content Intent** pour que le bot lise les messages. Puis invite-le : **OAuth2 → URL Generator**, portée `bot`, les permissions nécessaires (View Channels, Send Messages, Read Message History), ouvre l'URL et choisis le serveur.

## Bon à savoir

C'est le côté REST seulement : le bot lit et écrit à la demande, il n'écoute pas en direct. Supprimer et bannir demandent ta confirmation.
