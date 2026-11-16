# qBittorrent

Gibt einem Agenten Zugriff auf deinen BitTorrent-Client: Torrents auflisten,
Übertragungsraten beobachten, pausieren, hinzufügen, löschen.

## Was du brauchst

Zwei Dinge, beide aus qBittorrent selbst:

| Feld | Wo du es findest |
| --- | --- |
| Basis-URL | Die Adresse des Webinterface, **gefolgt von `/api/v2`** |
| Benutzername, Passwort | Tools → Options → Web UI (Werkzeuge → Optionen → Webinterface) |

## Die Basis-URL

Das ist der eine Punkt, der schiefgeht. Die Adresse muss auf die API zeigen,
nicht auf die Seite:

```
http://127.0.0.1:8080/api/v2      ✅
http://127.0.0.1:8080             ❌ every call returns 404
```

Läuft qBittorrent auf einer anderen Maschine, ersetze `127.0.0.1` durch deren
Adresse und stelle sicher, dass „Web User Interface (Remote control)“
(Webinterface, Fernsteuerung) in den Optionen aktiviert ist – sonst lauscht von
außen nichts.

## Die localhost-Falle

qBittorrent aktiviert standardmäßig **„Bypass authentication for clients on
localhost“** (Authentifizierung für Clients auf localhost umgehen).

Die Folge: Läuft Allkin auf derselben Maschine, gelingt die Verbindung **selbst
mit falschem Passwort**. Der Test wird grün, und er lügt nicht – er beweist nur,
dass die Maschine stimmt, nicht deine Zugangsdaten.

Das macht nichts kaputt. Aber an dem Tag, an dem du qBittorrent woandershin
verlegst, bricht die Verbindung auf einen Schlag ab: Das Passwort war nie
geprüft worden. Entferne das Häkchen, wenn der Test etwas aussagen soll.

## Was der Agent tun darf und was du freigibst

Lesen und Einstellen braucht keine Freigabe: Torrent-Liste, Übertragungsraten,
Pause, Fortsetzen, Kategorien, Prioritäten. All das lässt sich mit einem Klick
rückgängig machen.

Fünf Vorgänge laufen über deine Freigabe, in der Unterhaltung:

- **einen Torrent hinzufügen** – belegt sofort Speicherplatz und Bandbreite
- **löschen** – mit `deleteFiles=true` verschwinden die heruntergeladenen Dateien von der Platte
- **die Dateien eines Torrents verschieben**
- **die Konfiguration ändern** – die Einstellungen umfassen die Authentifizierung des Webinterface
- **qBittorrent beenden**

Das ist keine Anweisung an den Agenten: Der Code fängt den Aufruf ab. Kein Agent
kann sich dem entziehen.

## Passwort und Sitzung

Das Passwort wird einmal verwendet, um die Sitzung zu öffnen. Danach ist ein
Cookie unterwegs, das automatisch erneuert wird und sich von qBittorrent aus
widerrufen lässt, ohne das Passwort zu ändern. Der Agent sieht keines von
beiden.
