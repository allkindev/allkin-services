# Soniox

Spracherkennung, live und für aufgezeichnete Dateien, mit Trennung der Sprecher. Abrechnung pro Stunde Audio.

## Der Schlüssel

**<https://console.soniox.com>** → ein Projekt → **API Keys → Create API key**.

## Gut zu wissen

Ein Soniox-Projekt lebt in **einer Region**, und sein Schlüssel funktioniert nur dort. Die vorausgefüllte Adresse ist die der Vereinigten Staaten; für ein Projekt in einer anderen Region ersetzen Sie sie durch `https://api.eu.soniox.com` (Europäische Union), `https://api.jp.soniox.com` (Japan) oder `https://api.in.soniox.com` (Indien). Ein Schlüssel gegen die falsche Region wird wie ein falscher Schlüssel abgelehnt.

Das Mithören eines Mikrofons läuft über das Plugin **Recordr**: Wählen Sie diesen Dienst in dessen Einstellungen. Der Ton geht dann vom Browser direkt zu Soniox, mit einem Schlüssel, der zwei Minuten gilt; der echte Schlüssel bleibt in Allkin.

Ein Agent, dem dieser Dienst gewährt wird, kann eine per URL erreichbare Aufnahme transkribieren. Eine Datei auf der Festplatte des Agenten lässt sich über dieses Relais nicht senden.
