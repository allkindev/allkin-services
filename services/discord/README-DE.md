# Discord

Server, Kanäle und Nachrichten über einen eigenen Bot.

## Der Bot

**<https://discord.com/developers/applications>** → **New Application → Bot → Reset Token**: das Token. Unter *Privileged Gateway Intents* **Message Content Intent** aktivieren, damit der Bot Nachrichten lesen kann. Dann einladen: **OAuth2 → URL Generator**, Bereich `bot`, die nötigen Rechte (View Channels, Send Messages, Read Message History), die URL öffnen und den Server wählen.

## Gut zu wissen

Das ist nur die REST-Seite: Der Bot liest und schreibt auf Anfrage, er hört nicht live zu. Löschen und Bannen fragen nach deiner Bestätigung.
