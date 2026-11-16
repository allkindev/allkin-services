# Autre service OAuth2

L'entrée passe-partout pour un service qui s'authentifie par OAuth2 sans figurer
au catalogue.

## Ce qu'il faut renseigner

- **URL d'autorisation** et **URL de jeton** — les deux points d'entrée OAuth2
  du service, donnés par sa documentation.
- **Identifiant** et **secret client** — obtenus en déclarant une application
  chez lui.
- **Portées** — séparées par des espaces.

## L'URI de redirection

L'adresse affichée dans l'onglet « Service » doit être recopiée **à l'identique**
dans la configuration de l'application, côté fournisseur. C'est la cause quasi
systématique des refus à la connexion : un port différent, une barre finale en
trop, et l'autorisation est rejetée.

## Bon à savoir

Cette entrée suppose le flux « au nom d'un utilisateur » : un bouton
« Se connecter », une redirection, un retour. Un service qui s'authentifie
lui-même — compte de service, `client_credentials` — ne se configure pas ici ;
il lui faut sa propre entrée au catalogue, comme OVHcloud.
