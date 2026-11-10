# SearXNG

Die Websuche Ihrer Agenten über Ihr eigenes SearXNG: Es befragt mehrere
Suchmaschinen gleichzeitig, von Ihrer Maschine aus, ohne Schlüssel und ohne
Kontingent.

## Was nötig ist

Die **SearXNG-Integration** von Allkin (Integrationen → Hinzufügen → SearXNG),
installiert, mit erteilten Rechten und gestartetem Dienst. Sie installiert und
startet SearXNG selbst auf der Maschine; dieser Dienst ist der Weg, über den
die Agenten es erreichen.

## Die Adresse

`http://127.0.0.1:9350` — der Port ist der **Lokale Port** aus den
Einstellungen der Integration (9350, wenn Sie ihn nicht geändert haben). Es
gibt keinen Schlüssel einzufügen.

## Einem Agenten geben

Auf der Seite des Agenten, unter seinen Diensten, **SearXNG** ankreuzen. Der
Agent sucht dann über diesen Dienst im Web, in Nachrichten, Bildern und Videos.

## Wenn der Test fehlschlägt

- **Keine Antwort**: Die Integration ist nicht gestartet — öffnen Sie ihre
  Seite, erteilen Sie die Rechte und starten Sie sie.
- **„not-ready“**: SearXNG wird noch installiert (beim ersten Mal einige
  Minuten) oder startet gerade. Warten Sie und testen Sie erneut.
- **Ein falscher Port**: Die Adresse muss den Port aus den Einstellungen der
  Integration tragen.

## Gut zu wissen

Suchmaschinen lehnen die Anfragen eines Servers manchmal eine Zeit lang ab (ein
CAPTCHA, eine Zeitüberschreitung): Eine Suche kommt dann mit weniger
Ergebnissen zurück und sagt, welche Suchmaschinen nicht geantwortet haben.
Dieser Dienst richtet sich nicht an ein anders installiertes SearXNG: Er
spricht mit der Integration, die kürzer antwortet als die API von SearXNG.
