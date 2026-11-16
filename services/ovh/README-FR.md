# OVHcloud — compte de service

Domaines, hébergements, serveurs dédiés, VPS, Public Cloud : l'API OVHcloud
expose à peu près tout ce que le manager sait faire.

> **Compte de service, pas clé API.** Ce sont deux dispositifs différents chez
> OVH, et c'est la confusion la plus fréquente. La page `api.ovh.com/createToken`
> que renvoient tous les tutoriels donne **trois** valeurs et relève de l'autre
> service du catalogue, « OVHcloud (clés API) ». Un compte de service en donne
> **deux**.

## Créer le compte de service

Manager → **Identité, sécurité et opérations** → **Identités** → **Compte de
service** → « Ajouter un compte de service ».

- Le **nom que tu choisis est l'identifiant client**.
- Le **mot de passe affiché est le secret**, montré une seule fois.

## L'étape qu'on oublie, et qui rend l'agent aveugle

Un compte de service tout neuf part **sans aucune ressource**. La connexion
réussit, l'agent interroge l'API, et reçoit des listes vides — pas un refus, un
`HTTP 200` avec zéro résultat. Rien ne signale qu'il manque quelque chose : ça
ressemble à un compte vide.

Il faut lui attribuer des droits, dans **Politiques** (même section du manager) :
crée une politique, choisis les ressources concernées, et rattache-lui le compte
de service.

C'est là que beaucoup s'arrêtent, parce que cette interface est capricieuse. Si
tu n'y arrives pas, prends l'autre voie : **« OVHcloud (clés API) »** dans le
catalogue, dont les droits se cochent au moment où l'on crée les clés.

## Ce que l'agent ne fait pas seul

Vingt-huit motifs d'appel passent par ta validation — l'achat et le paiement
d'une commande, la résiliation d'un service, la suppression d'une zone DNS, la
réinstallation d'un serveur. L'agent peut les préparer et te les soumettre ; il
ne peut pas les déclencher.

Le reste — lire le catalogue, consulter tes produits, préparer un panier — passe
sans rien demander.

## Bon à savoir

- Les valeurs par défaut visent l'**Europe** (`eu.api.ovh.com`). Un compte
  canadien ou américain a sa propre racine d'API.
- Les informations du compte (`/me`) sont refusées par défaut à un compte de
  service, alors que les produits restent accessibles. Un `403` sur `/me` n'est
  donc pas le signe d'une mauvaise configuration.
