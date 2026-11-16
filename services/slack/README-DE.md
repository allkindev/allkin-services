# Slack

Nachrichten und Channels, im Namen eines Bots.

## Das Token

**<https://api.slack.com/apps>** → deine App → **OAuth & Permissions** →
**Bot User OAuth Token**. Es beginnt mit `xoxb-`.

## Scopes

Hier entscheidet sich alles. Das Token kann nur, was seine Scopes erlauben, und
Slack gewährt sie nicht rückwirkend: Wer einen Scope hinzufügt, muss die App neu
im Workspace installieren.

Die gängigen:

| Scope | Wofür |
| --- | --- |
| `chat:write` | Nachrichten posten |
| `channels:read` | öffentliche Channels auflisten |
| `channels:history` | die Nachrichten eines öffentlichen Channels lesen |
| `users:read` | IDs in Namen auflösen |

## Gut zu wissen

Der Bot muss **in einen Channel eingeladen** sein, um dort zu lesen oder zu
schreiben, selbst mit den richtigen Scopes. `/invite @your-bot` im Channel.
