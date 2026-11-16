# Google Drive

Deine Dateien und Ordner: suchen, lesen, exportieren, ordnen, freigeben.

## Die Anwendung

Dieselbe Google-Cloud-Anwendung wie bei jedem anderen Google-Dienst von Allkin: **<https://console.cloud.google.com>** → ein Projekt → **APIs und Dienste → Anmeldedaten → Anmeldedaten erstellen → OAuth-Client-ID**, Typ **Webanwendung**, mit der im Reiter „Dienst“ gezeigten Umleitungs-URI zeichengenau kopiert. Hier Client-ID und Geheimnis eingeben, Bereiche anhaken, **Verbinden**.

Aktiviere **Google Drive API** in der **Bibliothek** desselben Projekts: Ein Bereich auf einer deaktivierten API ergibt eine Ablehnung, die nicht sagt, warum.

Solange der Zustimmungsbildschirm auf *Test* steht, können nur Testnutzer autorisieren und das Token stirbt nach sieben Tagen: Auf *Produktion* umstellen für eine dauerhafte Verbindung. Siehe die Hilfe von „Google (alle APIs)“ für die Details.

## Gut zu wissen

„Die Dateien, die der Agent anlegt“ beschränkt ihn auf sein Eigenes; „Alle Dateien“ öffnet das ganze Drive. Freigeben und Löschen fragen nach deiner Bestätigung. Neue Dateien hochzuladen bietet dieses Relais nicht.
