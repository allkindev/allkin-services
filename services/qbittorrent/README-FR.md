# qBittorrent

Donne à un agent l'accès à ton client BitTorrent : lister les torrents, suivre
les débits, mettre en pause, ajouter, supprimer.

## Ce qu'il te faut

Deux choses, prises dans qBittorrent lui-même :

| Champ | Où le trouver |
| --- | --- |
| URL de base | L'adresse de l'interface web, **suivie de `/api/v2`** |
| Nom d'utilisateur, mot de passe | Outils → Options → Web UI |

## L'URL de base

C'est le seul point qui se rate. L'adresse doit désigner l'API, pas la page :

```
http://127.0.0.1:8080/api/v2      ✅
http://127.0.0.1:8080             ❌ tous les appels répondent 404
```

Si qBittorrent tourne sur une autre machine, remplace `127.0.0.1` par son
adresse — et vérifie que « Web User Interface (Remote control) » est bien
activé dans les options, sinon rien n'écoute depuis l'extérieur.

## Le piège du « localhost »

qBittorrent coche par défaut **« Contourner l'authentification pour les clients
sur localhost »**.

Conséquence : si Allkin tourne sur la même machine, la connexion réussit **même
avec un mauvais mot de passe**. Le test s'affiche en vert, et il dit vrai — il
prouve seulement que la machine est la bonne, pas que tes identifiants le sont.

Ça ne gêne pas le fonctionnement. Mais le jour où tu déplaces qBittorrent
ailleurs, la connexion cassera d'un coup : c'est le mot de passe qui n'avait
jamais été vérifié. Décoche l'option si tu veux que le test ait du sens.

## Ce que l'agent peut faire, et ce que tu valides

Lire et régler ne demande rien : liste des torrents, débits, pause, reprise,
catégories, priorités. Tout cela se défait d'un clic.

Cinq opérations passent par ta validation, dans le fil de la conversation :

- **ajouter un torrent** — occupe le disque et la bande passante immédiatement
- **supprimer** — avec `deleteFiles=true`, les fichiers téléchargés disparaissent du disque
- **déplacer les fichiers** d'un torrent
- **modifier la configuration** — les préférences incluent l'authentification de l'interface
- **arrêter qBittorrent**

Ce n'est pas une consigne donnée à l'agent : c'est le code qui intercepte
l'appel. Un agent ne peut pas s'en dispenser, même en auto-approbation d'une
autre nature.

## Mot de passe et session

Le mot de passe ne sert qu'une fois, à l'ouverture de la session. Ce qui voyage
ensuite est un cookie, renouvelé automatiquement — révocable côté qBittorrent
sans changer le mot de passe. L'agent, lui, ne voit ni l'un ni l'autre.

