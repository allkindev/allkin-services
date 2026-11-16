# Matrix

Räume und Nachrichten eines Matrix-Homeservers (Synapse, Conduit, Dendrite…).

## Das Token

Ein Zugriffstoken des Kontos, als das der Agent spricht – am besten ein
eigenes Bot-Konto. In Element: **Einstellungen → Hilfe & Über → Erweitert →
Zugriffstoken**. Oder per Anmeldung über die API:

```
POST https://<homeserver>/_matrix/client/v3/login
{"type":"m.login.password","identifier":{"type":"m.id.user","user":"bot"},"password":"…"}
```

Die Adresse ist die des Homeservers (`https://matrix.example.org`), nicht die
von Element.

## Gut zu wissen

Verschlüsselte Räume lassen sich so nicht lesen: Der Agent kann nur
unverschlüsselte Räume nutzen. Das Verlassen eines Raums und das Entfernen
einer Nachricht fragen nach deiner Bestätigung.
