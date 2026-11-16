# Jellyfin

Deine Mediathek: Bibliotheken, Filme, Serien, was gerade läuft.

## Der Schlüssel

**Dashboard** → **Erweitert** → **API-Schlüssel** → **+**.

## Die Basis-URL

Die Adresse deines Servers, so wie du sie im Browser öffnen würdest:

```
https://media.example.com        ✅
http://192.168.1.30:8096         ✅
```

Ohne Schrägstrich am Ende – Allkin entfernt ihn ohnehin, aber es ist gut zu
wissen: Genau dieser Schrägstrich erzeugt die `//` und die 404, wenn du die
Adresse aus der Adressleiste des Browsers einfügst.

## Gut zu wissen

Ein API-Schlüssel von Jellyfin hat Administratorrechte: Er sieht alle
Bibliotheken und alle Benutzer. Einen eingeschränkten Schlüssel gibt es nicht.
