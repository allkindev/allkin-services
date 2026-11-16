# OVHcloud – API-Schlüssel

Die alte Methode von OVH: drei Schlüssel und eine Signatur pro Anfrage.

**Das ist der Weg, wenn der Agent bestellen können soll.** An einem echten Konto
geprüft: Diese Schlüssel umgehen das IAM dort, wo ein Dienstkonto daran
scheitert. Sie handeln unter der Identität des Kontos selbst, mit der Rolle
ADMIN, statt unter einer neuen Identität ohne Rechte.

## Die Schlüssel erstellen

Öffne **<https://api.ovh.com/createToken/>**, angemeldet in deinem Konto.

| Feld | Wert |
| --- | --- |
| Script name | `allkin` |
| Validity | Unlimited |
| Rights | das nützliche Minimum |

Zu den Rechten: `GET` auf `/*` genügt einem Agenten, der liest. Füge `POST`,
`PUT` und `DELETE` auf `/*` nur hinzu, wenn der Agent schreiben muss – **diese
Rechte gelten für dein ganzes Konto**, ohne Unterschied zwischen den Produkten.

Die Seite gibt dann **drei Werte** zurück, die du in die drei Felder des Tabs
„Dienst“ einträgst. Sie werden nur einmal angezeigt.

## Der Tausch

Keine IAM-Richtlinie anzulegen: Die Rechte, die du ankreuzt, gelten ab der
ersten Anfrage. Genau darin liegt der Sinn dieses Wegs.

Im Gegenzug sind diese Schlüssel weit gefasst. Was den Agenten hier begrenzt,
ist nicht OVH, sondern Allkin: Es fängt Kauf, Zahlung, Kündigung und Löschung ab
und legt sie dir vor. Schränke die Muster trotzdem ein, statt alles anzukreuzen
– eine Schutzvorkehrung ist besser, wenn sie nicht die einzige ist.

## Gut zu wissen

Die Signatur berechnet Allkin bei jedem Aufruf, über Methode, URL und Body. Das
Application Secret verlässt die Maschine nie: Es fließt nur in den Hash ein.
