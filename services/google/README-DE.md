# Google

Gmail, Kalender, Drive, Sheets – über OAuth2, im Namen deines Kontos.

## Die Anmeldedaten erstellen

**<https://console.cloud.google.com>** → ein Projekt → **APIs & Dienste** →
**Anmeldedaten** → **Anmeldedaten erstellen** → **OAuth-Client-ID** → Typ
**Webanwendung**.

## Die Weiterleitungs-URI

Das ist Fehler Nummer eins (`redirect_uri_mismatch`). Die Adresse, die im Tab
„Dienst“ steht, muss **exakt** unter „Autorisierte Weiterleitungs-URIs“
eingetragen werden, Zeichen für Zeichen: Protokoll, Port und der fehlende
Schrägstrich am Ende zählen alle.

Wenn du Allkin unter mehreren Adressen öffnest (Domainname, IP-Adresse,
`localhost`), trage sie alle ein: Google vergleicht mit der, über die du
gekommen bist, nicht mit einer bevorzugten.

## Die APIs aktivieren

Jeder Google-Dienst ist eine eigene API und wird einzeln unter **Bibliothek**
aktiviert: Gmail API, Google Calendar API, Google Drive API, Google Sheets API.
Ein Berechtigungsumfang, der für eine deaktivierte API gewährt wurde, führt zu
einer Ablehnung, die nicht sagt, warum.

## Berechtigungsumfänge

Kreuze nur an, was der Agent braucht. `gmail.readonly` genügt, um ein Postfach
zu lesen; gib Schreibzugriff nur, wenn der Agent wirklich senden muss.

Wer die Berechtigungsumfänge eines bereits verbundenen Dienstes ändert, macht
dessen Token ungültig: Du musst erneut auf „Verbinden“ klicken.

## Zustimmungsbildschirm

Solange die App im Modus **Test** ist, können nur Konten sie autorisieren, die
als „Testnutzer“ eingetragen sind, und das Aktualisierungstoken läuft nach
sieben Tagen ab. Stelle die App auf **Produktion** um, wenn die Verbindung
dauerhaft halten soll.
