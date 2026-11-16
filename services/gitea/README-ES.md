# Gitea / Forgejo

Repositorios, issues, pull requests, releases: en Gitea o Forgejo, misma API.

## El token

**Configuración → Aplicaciones → Generar nuevo token**, con los ámbitos que
necesita el agente (`read:repository`, `write:issue`…). La dirección es la
raíz de tu instancia.

## Conviene saber

Eliminar un repositorio pide tu confirmación y dice lo que implica. La API
calca la de GitHub: un agente acostumbrado a una se orienta en la otra.
