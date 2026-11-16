# Autre service à clé API

L'entrée passe-partout : n'importe quelle API REST qui s'authentifie par une clé
constante.

## Ce qu'il faut renseigner

**L'URL de base** — la racine de l'API, sans barre finale. Les chemins que
l'agent donnera y seront ajoutés :

```
https://api.exemple.fr/v1
```

**Où placer la clé** — trois formes couvrent la quasi-totalité des API :

| Placement | Ce que ça donne | Exemple |
| --- | --- | --- |
| En-tête | `Authorization: Bearer <clé>` | la majorité |
| Paramètre | `?api_key=<clé>` | météo, indexeurs |
| Chemin | l'URL contient `{secret}` | Telegram |

Les réglages fins — nom de l'en-tête, préfixe, suffixe — servent aux formats
inhabituels, du genre `X-Emby-Token: <clé>` ou
`Authorization: MediaBrowser Token="<clé>"`.

## Ce qui aide vraiment

Le champ **« Consignes aux agents »**. Un agent qui découvre une API inconnue n'a
aucune documentation : deux lignes sur les endpoints utiles lui épargnent une
demi-douzaine d'appels à tâtons — et te les épargnent aussi, puisque chacun se
paie.

## Bon à savoir

Si l'API que tu veux brancher revient souvent, elle mérite sa propre entrée au
catalogue : un dossier sous `src/services/`, un fichier `index.ts`, et ce
README. Elle apparaîtra alors partout avec son logo, son aide et ses garde-fous.
