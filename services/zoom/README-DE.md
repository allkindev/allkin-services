# Zoom

Meetings, Aufzeichnungen, Benutzer und Berichte deines Zoom-Kontos.

## Die Anwendung

Eine **Server-to-Server-OAuth**-App: **<https://marketplace.zoom.us>** → **Develop → Build App → Server-to-Server OAuth**. Ihre Seite *App Credentials* liefert drei Werte: **Account ID**, **Client ID**, **Client Secret**. Die nötigen Bereiche hinzufügen (meeting:read:admin, meeting:write:admin, recording:read:admin…) und die App aktivieren. Die drei Werte eingeben; *Testen* holt ein Token.

## Gut zu wissen

Das Token lebt eine Stunde und wird von Allkin erneuert. Ein Meeting absagen oder eine Aufzeichnung löschen fragt nach deiner Bestätigung.
