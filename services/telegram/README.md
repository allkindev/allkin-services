# Telegram

An outbound channel: the agent sends messages, it receives none.

## Creating the bot

Message **@BotFather** on Telegram, command `/newbot`. It returns a token
shaped like `123456789:AAE...`.

## The chat ID

This is the most important field, and the only one requiring a manual step.

1. Send a message to your bot (or add it to a group and post there).
2. Open `https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates`.
3. Read `chat.id` — **negative** for a group, positive for a direct chat.

## Why this field is enforced

A Telegram bot key can write to **any** conversation the bot knows. The ID you
enter here is rewritten by Allkin into every call, overriding whatever the agent
supplied.

In other words: this is not an instruction, it is a constraint. The bot can only
ever write to this conversation, whatever an agent asks.

## Good to know

The "Send a test message" button on the service card sends a real message. It is
the only way to check the destination — a valid key does not prove the message
lands in the right place.
