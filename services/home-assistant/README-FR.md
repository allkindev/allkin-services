# Home Assistant

Donne à un agent l'état de ta maison, et de quoi agir dessus.

## L'URL de base

Celle de ton Home Assistant, **port compris**, et **sans `/api` à la fin** :

```
http://192.168.1.20:8123         ✅
http://192.168.1.20:8123/api     ❌
```

## Le jeton

Clique sur **ton nom en bas de la barre latérale** → onglet **Sécurité** → tout
en bas, **« Créer un jeton »**. Il est affiché une seule fois.

C'est un jeton de longue durée lié à ton compte : il a les mêmes droits que toi.
Home Assistant ne sait pas en délivrer un plus étroit — si tu veux borner ce
qu'un agent peut faire, crée-lui un utilisateur Home Assistant dédié et prends
le jeton depuis ce compte-là.

## Appels utiles

| Appel | Ce qu'il fait |
| --- | --- |
| `GET /api/states` | l'état de tout |
| `GET /api/states/light.salon` | l'état d'une entité |
| `POST /api/services/light/turn_on` | allume, avec `{"entity_id": "light.salon"}` |

`GET /api/states` renvoie souvent plusieurs centaines d'entités. L'agent sait
n'en extraire que ce qu'il cherche — inutile de lui faire tout lire.

## Ce qui aide vraiment un agent

Le champ **« Consignes aux agents »** de l'onglet Service. Aucune documentation
générique ne peut savoir que ton salon s'appelle `light.salon_principal` : c'est
souvent la seule chose qui manque pour viser juste du premier coup.
