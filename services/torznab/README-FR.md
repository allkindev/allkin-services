# Torznab

Norme d'interrogation des indexeurs — Prowlarr, Jackett, et la plupart des
trackers qui exposent une API de recherche.

## L'URL de base

C'est **l'adresse exacte de l'API**, pas le nom de domaine du site. Une API
Torznab n'a pas de chemin : tout se joue dans les paramètres, et l'adresse que
tu donnes est appelée telle quelle.

```
https://monsite.org/api          ✅
https://monsite.org              ❌ tu obtiendras la page d'accueil du site
```

Le test le vérifie : il envoie `?t=caps` — la seule requête que la norme impose
à tout indexeur — et refuse une réponse qui n'est pas du Torznab. Une page web
ne passe donc plus pour une API.

Où trouver l'adresse :

- **Indexeur public** : ta page de profil, avec la clé.
- **Prowlarr** : bouton « Copy Torznab Url » sur l'indexeur ; clé dans
  Settings → General.
- **Jackett** : bouton « Copy Torznab Feed » ; clé en haut du tableau de bord.

Elle finit souvent par `/api`, parfois par quelque chose comme
`/api/v2.0/indexers/…/results/torznab`.

## Ce que l'agent en fait

Il commence toujours par `?t=caps`, qui lui dit quelles recherches et quelles
catégories l'indexeur accepte — cela varie de l'un à l'autre. Ensuite
`?t=search&q=…`, `?t=tvsearch`, `?t=movie`.

L'indexeur répond en XML ; **Allkin le convertit en JSON** avant de le rendre à
l'agent. Ce n'est pas du confort : c'est ce qui lui permet de n'extraire que ce
qu'il veut. Une recherche de vingt-cinq résultats pèse plus de 20 000
caractères, et ce qui entre dans une conversation s'y paie à chaque tour ensuite.
Demandée en extrayant les seuls titres, elle en fait 1 200.

Chaque résultat porte un lien de téléchargement que l'agent enregistre
directement dans ses fichiers, en `.torrent`.

## Ta clé ne part pas dans le contexte

Beaucoup d'indexeurs répètent la clé en clair dans le lien de téléchargement de
**chaque** résultat. Une seule recherche suffirait à la déposer des dizaines de
fois dans la conversation de l'agent, où elle resterait.

Allkin la remplace avant que la réponse n'atteigne le modèle. Mesuré sur une
recherche réelle : vingt-cinq occurrences masquées, zéro en clair.
