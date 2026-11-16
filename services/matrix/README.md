# Matrix

Rooms and messages of a Matrix homeserver (Synapse, Conduit, Dendrite…).

## The token

An access token of the account the agent will speak as — best a dedicated
bot account. In Element: **Settings → Help & About → Advanced → Access
Token**. Or by logging in through the API:

```
POST https://<homeserver>/_matrix/client/v3/login
{"type":"m.login.password","identifier":{"type":"m.id.user","user":"bot"},"password":"…"}
```

The address is the homeserver's (`https://matrix.example.org`), not the
Element one.

## Good to know

Encrypted rooms cannot be read this way: the agent can only use unencrypted
rooms. Leaving a room and removing a message ask for your confirmation.
