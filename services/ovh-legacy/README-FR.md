# OVHcloud — clés API

La méthode historique d'OVH : trois clés et une signature par requête.

**C'est la voie à prendre si tu veux que l'agent puisse commander.** Vérifié sur
un compte réel : ces clés contournent l'IAM là où un compte de service s'y
heurte. Elles agissent sous l'identité du compte, avec le rôle ADMIN, et non
sous une identité neuve dépourvue de droits.

## Créer les clés

Ouvre **<https://api.ovh.com/createToken/>**, connecté à ton compte.

| Champ | Valeur |
| --- | --- |
| Script name | `allkin` |
| Validity | Unlimited |
| Rights | le minimum utile |

Pour les droits : `GET` sur `/*` suffit à un agent qui lit. N'ajoute `POST`,
`PUT` et `DELETE` sur `/*` que si l'agent doit écrire — **ces droits-là valent
sur tout ton compte**, sans distinction de produit.

La page rend ensuite **trois valeurs**, à reporter dans les trois champs de
l'onglet « Service ». Elles ne sont affichées qu'une fois.

## Ce que tu échanges

Aucune politique IAM à créer : les droits cochés sont acquis dès la première
requête. C'est tout l'intérêt de cette voie.

En contrepartie ces clés sont larges. Ce qui borne l'agent, ici, ce n'est pas
OVH : c'est Allkin, qui intercepte l'achat, le paiement, la résiliation et la
suppression pour te les soumettre. Restreins quand même les motifs plutôt que de
tout cocher — un garde-fou vaut mieux quand il n'est pas seul.

## Bon à savoir

La signature est calculée par Allkin à chaque appel, sur la méthode, l'URL et le
corps. L'application secret ne quitte jamais la machine : il ne sert qu'à
calculer l'empreinte.
