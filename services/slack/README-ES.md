# Slack

Mensajes y canales, en nombre de un bot.

## El token

**<https://api.slack.com/apps>** → tu aplicación → **OAuth & Permissions** →
**Bot User OAuth Token**. Empieza por `xoxb-`.

## Ámbitos

Aquí se decide todo. El token solo puede hacer lo que sus ámbitos permiten, y
Slack no los concede con efecto retroactivo: añadir un ámbito obliga a
reinstalar la aplicación en el espacio de trabajo.

Los más habituales:

| Ámbito | Para |
| --- | --- |
| `chat:write` | publicar mensajes |
| `channels:read` | listar los canales públicos |
| `channels:history` | leer los mensajes de un canal público |
| `users:read` | convertir los identificadores en nombres |

## Conviene saber

El bot debe estar **invitado a un canal** para leer o escribir en él, incluso
con los ámbitos adecuados. `/invite @your-bot` en el canal.
