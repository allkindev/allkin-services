# Jellyfin

Ta médiathèque : bibliothèques, films, séries, ce qui est en cours de lecture.

## La clé

**Tableau de bord** → **Avancé** → **Clés API** → **+**.

## L'URL de base

Celle de ton serveur, telle que tu l'ouvres dans un navigateur :

```
https://media.chezmoi.fr         ✅
http://192.168.1.30:8096         ✅
```

Sans barre oblique finale — Allkin la retire de toute façon, mais autant le
savoir : c'est elle qui produit les `//` et les 404 quand on colle l'adresse
depuis la barre du navigateur.

## Bon à savoir

Une clé API Jellyfin a les droits d'un administrateur : elle voit toutes les
bibliothèques et tous les utilisateurs. Il n'y a pas de clé restreinte.
