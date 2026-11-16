# Wikidata

Die strukturierte Wissensbasis hinter Wikipedia: Entitäten, Eigenschaften und
ein SPARQL-Endpunkt für Fragen über viele Elemente hinweg.

## Nichts einzugeben

Kein Schlüssel. Der Test sucht „Earth“ und erwartet eine Entität zurück.

## Gut zu wissen

SPARQL-Abfragen antworten auf `query.wikidata.org`, das der Agent über diesen
Dienst erreichen darf. Lange Abfragen laufen nach einer Minute ab: Der Agent
soll sie klein halten.
