# Paperless-ngx

Deine Dokumente: Volltextsuche, Tags, Korrespondenten, Dokumenttypen.

## Das Token

**Profil (oben rechts) → API-Auth-Token → erzeugen**. Oder auf der Maschine:
`manage.py drf_create_token <benutzer>`. Die Adresse ist die der
Weboberfläche.

## Gut zu wissen

Pfade enden mit einem Schrägstrich, die API ist paginiert (25 als Standard).
Das Löschen eines Dokuments fragt nach deiner Bestätigung; der Papierkorb
behält es ohnehin eine Weile.
