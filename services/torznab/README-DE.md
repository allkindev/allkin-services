# Torznab

Der Standard zur Abfrage von Indexern – Prowlarr, Jackett und die meisten
Tracker, die eine Such-API anbieten.

## Die Basis-URL

Das ist die **genaue Adresse der API**, nicht der Domainname der Website. Eine
Torznab-API hat keinen Pfad: Alles geschieht in den Abfrageparametern, und die
Adresse, die du angibst, wird unverändert aufgerufen.

```
https://mysite.org/api           ✅
https://mysite.org               ❌ you will get the site's home page
```

Der Test prüft das: Er sendet `?t=caps` – die eine Anfrage, die der Standard von
jedem Indexer verlangt – und weist eine Antwort zurück, die nicht Torznab ist.
Eine Webseite geht nicht mehr als API durch.

Wo du die Adresse findest:

- **Öffentlicher Indexer**: deine Profilseite, neben dem Schlüssel.
- **Prowlarr**: Schaltfläche „Copy Torznab Url“ beim Indexer; Schlüssel unter
  Settings → General.
- **Jackett**: Schaltfläche „Copy Torznab Feed“; Schlüssel oben im Dashboard.

Sie endet oft auf `/api`, manchmal auf etwas wie
`/api/v2.0/indexers/…/results/torznab`.

## Was der Agent damit macht

Er beginnt immer mit `?t=caps`, das ihm sagt, welche Suchen und Kategorien der
Indexer annimmt – das ist von einem zum anderen verschieden. Dann
`?t=search&q=…`, `?t=tvsearch`, `?t=movie`.

Der Indexer antwortet in XML; **Allkin wandelt es in JSON um**, bevor der Agent
es bekommt. Das dient nicht der Bequemlichkeit: Erst dadurch kann der Agent nur
das herausholen, was er will. Eine Suche mit fünfundzwanzig Ergebnissen wiegt
über 20.000 Zeichen, und was in eine Unterhaltung gelangt, wird in jeder
späteren Runde erneut bezahlt. Fragt man nur nach den Titeln, kommt dieselbe
Suche mit 1.200 zurück.

Jedes Ergebnis trägt einen Download-Link, den der Agent direkt in seinen Dateien
speichert, als `.torrent`.

## Dein Schlüssel gelangt nicht in den Kontext

Viele Indexer wiederholen den Schlüssel im Klartext im Download-Link **jedes**
Ergebnisses. Eine einzige Suche würde ihn dutzendfach in der Unterhaltung des
Agenten ablegen, wo er bliebe.

Allkin ersetzt ihn, bevor die Antwort das Modell erreicht. Gemessen an einer
echten Suche: fünfundzwanzig Vorkommen maskiert, null im Klartext.
