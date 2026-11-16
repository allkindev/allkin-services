# Gitea / Forgejo

Repositories, Issues, Pull Requests, Releases – auf Gitea oder Forgejo, gleiche
API.

## Das Token

**Einstellungen → Anwendungen → Neues Token erzeugen**, mit den Bereichen, die
der Agent braucht (`read:repository`, `write:issue`…). Die Adresse ist die
Wurzel deiner Instanz.

## Gut zu wissen

Das Löschen eines Repositories fragt nach deiner Bestätigung und sagt, was es
bedeutet. Die API spiegelt die von GitHub: Ein Agent, der die eine kennt,
findet sich in der anderen zurecht.
