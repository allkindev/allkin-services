# YouTube

Dein Kanal: Videos, Playlists, Kommentare, Abos, Suche.

## Die Anwendung

Dieselbe Google-Cloud-Anwendung wie bei jedem anderen Google-Dienst von Allkin: **<https://console.cloud.google.com>** → ein Projekt → **APIs und Dienste → Anmeldedaten → Anmeldedaten erstellen → OAuth-Client-ID**, Typ **Webanwendung**, mit der im Reiter „Dienst“ gezeigten Umleitungs-URI zeichengenau kopiert. Hier Client-ID und Geheimnis eingeben, Bereiche anhaken, **Verbinden**.

Aktiviere **YouTube Data API v3** in der **Bibliothek** desselben Projekts: Ein Bereich auf einer deaktivierten API ergibt eine Ablehnung, die nicht sagt, warum.

Solange der Zustimmungsbildschirm auf *Test* steht, können nur Testnutzer autorisieren und das Token stirbt nach sieben Tagen: Auf *Produktion* umstellen für eine dauerhafte Verbindung. Siehe die Hilfe von „Google (alle APIs)“ für die Details.

## Gut zu wissen

Das Tageskontingent sind 10 000 Einheiten, eine Suche kostet 100: Der Agent soll sparsam suchen. Ein Video zu ändern und Löschen fragen nach deiner Bestätigung. Uploads bietet dieses Relais nicht.
