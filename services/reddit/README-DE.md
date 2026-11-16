# Reddit

Subreddits, Beiträge und Kommentare, lesend, über eine registrierte Anwendung.

## Die Anwendung

**<https://www.reddit.com/prefs/apps>** → **create another app** → Typ
**script**, ein beliebiger Name, redirect URI `http://localhost`. Die Id ist
die kurze Zeichenfolge unter dem Namen der Anwendung; das Secret steht daneben.

Trage sie als Client-Id und Client-Secret ein. „Testen“ holt ein Token bei
Reddit und liest ein öffentliches Subreddit: Das ist die ganze Verbindung.

## Gut zu wissen

Ein Anwendungs-Token liest nur öffentliche Inhalte: kein Posten, kein Abstimmen,
keine privaten Nachrichten. Reddit erlaubt etwa sechzig Aufrufe pro Minute und
Anwendung.
