# Jira

Incidencias, proyectos, tableros y sprints de Jira Cloud.

## La cuenta

Un token de API de tu cuenta Atlassian: **<https://id.atlassian.com/manage-profile/security/api-tokens>** → **Create API token**. Introduce el correo de la cuenta como usuario y el token como contraseña, y el nombre de tu sitio (la parte antes de `.atlassian.net`).

## Conviene saber

Descripciones y comentarios viajan en Atlassian Document Format, que el agente conoce. El mismo token sirve para Confluence. Jira Server o Data Center tiene otra API (`/rest/api/2`, token personal): usa la entrada genérica para él.
