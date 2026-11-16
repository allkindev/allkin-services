# Discord

Servers, channels and messages, through a bot of yours.

## The bot

**<https://discord.com/developers/applications>** → **New Application → Bot → Reset Token**: the token. Under *Privileged Gateway Intents*, enable **Message Content Intent** so the bot can read messages. Then invite it: **OAuth2 → URL Generator**, scope `bot`, the permissions it needs (View Channels, Send Messages, Read Message History), open the URL and pick the server.

## Good to know

This is the REST side only: the bot reads and writes on request, it does not listen live. Deleting and banning ask for your confirmation.
