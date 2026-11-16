# Home Assistant

Gibt einem Agenten den Zustand deines Zuhauses und die Mittel, darauf
einzuwirken.

## Die Basis-URL

Die Adresse deines Home Assistant, **mit Port** und **ohne `/api` am Ende**:

```
http://192.168.1.20:8123         ✅
http://192.168.1.20:8123/api     ❌
```

## Das Token

Klicke auf **deinen Namen unten in der Seitenleiste** → Tab **Sicherheit** →
ganz unten **„Token erstellen“**. Es wird nur einmal angezeigt.

Das ist ein langlebiges Token, das an dein Konto gebunden ist: Es hat genau
deine Rechte. Home Assistant kann kein engeres ausstellen – wenn du begrenzen
willst, was ein Agent tun kann, lege einen eigenen Home-Assistant-Benutzer an
und nimm das Token aus diesem Konto.

## Nützliche Aufrufe

| Aufruf | Was er tut |
| --- | --- |
| `GET /api/states` | der Zustand von allem |
| `GET /api/states/light.living` | der Zustand einer Entität |
| `POST /api/services/light/turn_on` | schaltet ein, mit `{"entity_id": "light.living"}` |

`GET /api/states` liefert oft mehrere hundert Entitäten. Der Agent kann sich nur
das herausholen, was er braucht – er muss nicht alles lesen.

## Was einem Agenten wirklich hilft

Das Feld **„Hinweise für die Agenten“** im Tab Dienst. Keine allgemeine
Dokumentation kann wissen, dass dein Wohnzimmer `light.main_living` heißt: Oft
fehlt nur das, um beim ersten Versuch richtig zu liegen.
