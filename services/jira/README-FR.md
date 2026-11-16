# Jira

Tickets, projets, tableaux et sprints de Jira Cloud.

## Le compte

Un jeton d'API de ton compte Atlassian : **<https://id.atlassian.com/manage-profile/security/api-tokens>** → **Create API token**. Saisis l'e-mail du compte comme identifiant et le jeton comme mot de passe, et le nom de ton site (la partie avant `.atlassian.net`).

## Bon à savoir

Descriptions et commentaires voyagent au format Atlassian Document Format, que l'agent connaît. Le même jeton sert pour Confluence. Jira Server ou Data Center a une autre API (`/rest/api/2`, jeton personnel) : prends l'entrée générique pour lui.
