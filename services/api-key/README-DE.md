# Anderer Dienst mit API-Schlüssel

Der Eintrag für alles Übrige: jede REST-API, die sich mit einem festen Schlüssel
authentifiziert.

## Was einzutragen ist

**Die Basis-URL** – die Wurzel der API, ohne Schrägstrich am Ende. Die Pfade,
die der Agent angibt, werden daran angehängt:

```
https://api.example.com/v1
```

**Wohin mit dem Schlüssel** – drei Formen decken fast alle APIs ab:

| Ort | Was dabei herauskommt | Beispiel |
| --- | --- | --- |
| Header | `Authorization: Bearer <key>` | die meisten |
| Abfrageparameter | `?api_key=<key>` | Wetter, Indexer |
| Pfad | die URL enthält `{secret}` | Telegram |

Die Feineinstellungen – Name des Headers, Präfix, Suffix – sind für
ungewöhnliche Formate da, etwa `X-Emby-Token: <key>` oder
`Authorization: MediaBrowser Token="<key>"`.

## Was wirklich hilft

Das Feld **„Hinweise für die Agenten“**. Ein Agent, der auf eine unbekannte API
trifft, hat keine Dokumentation: Zwei Zeilen über die nützlichen Endpunkte
ersparen ihm ein halbes Dutzend Aufrufe auf gut Glück – und dir auch, denn jeder
davon kostet.

## Gut zu wissen

Wenn die API, die du anbinden willst, oft wiederkehrt, verdient sie einen
eigenen Katalogeintrag: einen Ordner unter `src/services/`, eine `index.ts` und
dieses README. Dann erscheint sie überall mit ihrem Logo, ihrer Hilfe und ihren
Schutzvorkehrungen.
