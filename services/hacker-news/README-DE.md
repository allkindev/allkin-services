# Hacker News

Beiträge und Kommentare über die offizielle API, Suche über Algolia.

## Nichts einzugeben

Kein Schlüssel auf beiden Seiten. Der Test liest die Id des neuesten Elements.

## Gut zu wissen

Die offizielle API liefert nur Ids: Eine Startseite zu lesen bedeutet einen
Aufruf pro Beitrag, daher die Anweisung an den Agenten, bei den ersten
Dutzend aufzuhören. Suchen und Filtern nach Datum oder Punkten läuft über
`hn.algolia.com`, das über diesen Dienst erreichbar ist.
