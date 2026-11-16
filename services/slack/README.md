# Slack

Messages and channels, on behalf of a bot.

## The token

**<https://api.slack.com/apps>** → your app → **OAuth & Permissions** →
**Bot User OAuth Token**. It starts with `xoxb-`.

## Scopes

This is where everything is decided. The token can only do what its scopes
allow, and Slack does not grant them retroactively: adding a scope requires
reinstalling the app into the workspace.

The common ones:

| Scope | For |
| --- | --- |
| `chat:write` | posting messages |
| `channels:read` | listing public channels |
| `channels:history` | reading a public channel's messages |
| `users:read` | resolving IDs into names |

## Good to know

The bot must be **invited into a channel** to read or write there, even with the
right scopes. `/invite @your-bot` in the channel.
