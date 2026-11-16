# Slack

Messages et canaux, au nom d'un bot.

## Le jeton

**<https://api.slack.com/apps>** → ton application → **OAuth & Permissions** →
**Bot User OAuth Token**. Il commence par `xoxb-`.

## Les portées

C'est là que tout se joue. Le jeton ne peut faire que ce que ses portées
autorisent, et Slack ne les accorde pas rétroactivement : ajouter une portée
oblige à réinstaller l'application dans l'espace de travail.

Les plus courantes :

| Portée | Pour |
| --- | --- |
| `chat:write` | écrire des messages |
| `channels:read` | lister les canaux publics |
| `channels:history` | lire les messages d'un canal public |
| `users:read` | résoudre les identifiants en noms |

## Bon à savoir

Le bot doit être **invité dans un canal** pour y écrire ou y lire, même avec les
bonnes portées. `/invite @ton-bot` dans le canal concerné.
