# Gitea / Forgejo

Dépôts, issues, pull requests, releases — sur Gitea ou Forgejo, même API.

## Le jeton

**Paramètres → Applications → Générer un nouveau jeton**, avec les portées
dont l'agent a besoin (`read:repository`, `write:issue`…). L'adresse est la
racine de ton instance.

## Bon à savoir

Supprimer un dépôt demande ta confirmation et dit ce que ça implique. L'API
est calquée sur celle de GitHub : un agent habitué à l'une se retrouve dans
l'autre.
