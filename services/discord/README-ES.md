# Discord

Servidores, canales y mensajes, mediante un bot tuyo.

## El bot

**<https://discord.com/developers/applications>** → **New Application → Bot → Reset Token**: el token. En *Privileged Gateway Intents*, activa **Message Content Intent** para que el bot lea los mensajes. Luego invítalo: **OAuth2 → URL Generator**, ámbito `bot`, los permisos necesarios (View Channels, Send Messages, Read Message History), abre la URL y elige el servidor.

## Conviene saber

Es solo el lado REST: el bot lee y escribe a petición, no escucha en directo. Eliminar y expulsar piden tu confirmación.
