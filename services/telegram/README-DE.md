# Telegram

Ein Ausgangskanal: Der Agent sendet Nachrichten, er empfängt keine.

## Den Bot erstellen

Schreib **@BotFather** auf Telegram, Befehl `/newbot`. Er gibt dir ein Token der
Form `123456789:AAE...` zurück.

## Die Kennung der Unterhaltung

Das ist das wichtigste Feld, und das einzige, das einen Handgriff verlangt.

1. Schick deinem Bot eine Nachricht (oder füge ihn einer Gruppe hinzu und
   schreib dort).
2. Öffne `https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates`.
3. Lies `chat.id` ab – **negativ** bei einer Gruppe, positiv bei einem
   Direktchat.

## Warum dieses Feld erzwungen wird

Ein Bot-Schlüssel von Telegram kann in **jede** Unterhaltung schreiben, die der
Bot kennt. Die Kennung, die du hier einträgst, schreibt Allkin in jeden Aufruf
und überschreibt damit, was der Agent angegeben hat.

Anders gesagt: Das ist keine Anweisung, sondern eine Beschränkung. Der Bot kann
immer nur in diese Unterhaltung schreiben, egal was ein Agent verlangt.

## Gut zu wissen

Die Schaltfläche „Testnachricht senden“ auf der Karte des Dienstes sendet eine
echte Nachricht. Nur so lässt sich das Ziel prüfen – ein gültiger Schlüssel
beweist nicht, dass die Nachricht am richtigen Ort ankommt.
