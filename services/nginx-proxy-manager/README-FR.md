# Nginx Proxy Manager

Donne à un agent la main sur ton reverse proxy : lister les domaines publiés,
voir quel service chacun dessert, diagnostiquer une configuration qui ne charge
pas, publier un nouveau service, demander un certificat.

## Ce qu'il te faut

Deux choses, prises dans Nginx Proxy Manager lui-même :

| Champ | Où le trouver |
| --- | --- |
| URL de base | L'adresse de l'interface d'administration, **suivie de `/api`** |
| Adresse e-mail, mot de passe | Ceux avec lesquels tu te connectes à cette interface |

## L'URL de base

C'est le seul point qui se rate. L'adresse doit désigner l'API, pas la page :

```
http://127.0.0.1:81/api      ✅
http://127.0.0.1:81          ❌ « 405 Not Allowed », une page web au lieu de l'API
```

Le port **81** est celui de l'interface d'administration — à ne pas confondre
avec les ports 80 et 443, par lesquels passe le trafic des sites que le proxy
dessert. Si Nginx Proxy Manager tourne sur une autre machine, remplace
`127.0.0.1` par son adresse.

## Le compte à utiliser

Celui de l'interface web. Deux remarques :

- **La double authentification bloque cette connexion.** L'échange
  identifiant/mot de passe ne peut pas la franchir : le service répond qu'il
  attend un second facteur, et Allkin te le dira tel quel. Utilise un compte
  qui ne l'a pas activée.
- **L'adresse e-mail du compte sert aussi à Let's Encrypt.** C'est elle qui est
  envoyée à l'autorité de certification lors d'une demande — il n'y a pas de
  champ séparé pour ça.

Tu peux créer un compte dédié à Allkin (Users → Add User) plutôt que de donner
le tien : les droits se règlent par utilisateur, et un accès en lecture seule
suffit à un agent qui ne doit que surveiller.

## Ce que l'agent peut faire, et ce que tu valides

Lire ne demande rien : liste des hôtes, des certificats, des listes d'accès,
journal d'audit, rapports, diagnostic d'une configuration en erreur.

Tout ce qui change ce qu'Internet voit de la machine passe par ta validation,
dans le fil de la conversation :

| Ce que l'agent demande | Pourquoi ça se valide |
| --- | --- |
| Publier ou modifier un hôte | Un domaine devient joignable, ou se met à pointer ailleurs |
| Désactiver un hôte | Le domaine cesse de répondre |
| Supprimer une entrée | La configuration est effacée, pas désactivée : elle est à refaire |
| Demander un certificat | Let's Encrypt limite à 5 certificats identiques par semaine |
| Supprimer un certificat | Tous les hôtes qui s'en servent perdent le HTTPS |
| Ouvrir un flux TCP/UDP | Un port est relayé tel quel, sans domaine ni chiffrement |
| Toucher aux comptes ou aux réglages | Un mot de passe changé peut te verrouiller dehors |

Réactiver un hôte, en revanche, ne demande rien : on valide ce qui casse, pas
ce qui remet en état.

Ce n'est pas une consigne donnée à l'agent : c'est le code qui intercepte
l'appel. Un agent ne peut pas s'en dispenser.

Si tu veux aller plus loin, la case **« Lecture seule sur les services »** dans
les droits de l'agent ferme toute écriture d'un coup — l'outil ne monte alors
que les méthodes qui ne modifient rien.

## Mot de passe et session

Le mot de passe ne sert qu'une fois, pour obtenir un jeton. C'est ce jeton —
daté par Nginx Proxy Manager, renouvelé automatiquement à l'expiration — qui
voyage ensuite. L'agent ne voit ni l'un ni l'autre.

## Si quelque chose ne va pas

| Ce que tu lis | Ce que c'est |
| --- | --- |
| « connexion refusée » au test | Adresse e-mail ou mot de passe. Le service répond `Invalid email or password` |
| « la réponse est une page web » | Il manque `/api` à la fin de l'URL de base |
| « aucun champ `token` n'est revenu » | Le compte utilise la double authentification |
| « Connexion refusée : rien n'écoute » | Mauvais port — l'administration est sur 81, pas 80 |
