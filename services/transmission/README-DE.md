# Transmission

Torrents über das RPC des Daemons: auflisten, hinzufügen, starten, stoppen,
entfernen.

## Das Konto

Benutzername und Passwort der Weboberfläche (`rpc-username` und `rpc-password`
in `settings.json`, oder `USER`/`PASS` des Containers). Die Adresse ist die der
Weboberfläche, ohne `/transmission`.

## Gut zu wissen

Transmission schützt sein RPC mit einem Sitzungstoken: Allkin holt es und
schickt es von selbst zurück. Das Entfernen eines Torrents samt Daten lässt den
Agenten zuerst bei dir nachfragen.
