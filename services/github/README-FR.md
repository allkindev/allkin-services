# GitHub

Dépôts, issues, pull requests.

## Créer le jeton

**Settings** → **Developer settings** → **Personal access tokens**.

Les jetons « fine-grained » sont préférables : ils se limitent à des dépôts
choisis, là où un jeton classique vaut sur tout ton compte.

Donne-lui **le minimum de portées**. Un agent qui lit des issues n'a pas besoin
d'écrire dans le code ; un agent qui ouvre des pull requests n'a pas besoin
d'administrer l'organisation.

## Bon à savoir

Le jeton agit sous ton identité : ce que l'agent écrit apparaîtra sous ton nom,
avec ton avatar. Pour distinguer son travail du tien, crée un compte machine et
prends le jeton depuis celui-là.
