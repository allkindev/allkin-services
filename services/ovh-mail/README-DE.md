# OVHcloud Mail

Gibt einem Agenten vollen Zugriff auf ein OVH-Postfach: lesen, suchen, ablegen,
antworten, senden, löschen.

Alles, was der Agent tut, erscheint in deinem Webmail, denn es ist dasselbe
Postfach auf demselben Server. Der Agent geht nicht über die Webmail-Oberfläche.
Er spricht direkt mit diesem Server, per IMAP zum Lesen und per SMTP zum Senden.

## Was du brauchst

| Feld | Wert |
| --- | --- |
| Server | `ssl0.ovh.net` für **MX Plan** (vorausgefüllt); für **Email Pro** der im Manager angezeigte Server `proN.mail.ovh.net` |
| E-Mail-Adresse | die vollständige Adresse, `you@your-domain.com` |
| Passwort | das Passwort des Postfachs, dasselbe wie für das Webmail |

Die Schaltfläche „Hinzufügen“ prüft **Lesen** und **Senden** getrennt. Ein Konto
kann lesen und trotzdem nicht senden können: OVH sperrt das Senden aus einem
Postfach, das es des Spams verdächtigt, und die Prüfung sagt dir das.

## Was der Agent nicht allein tut

Drei Aktionen lassen sich nicht rückgängig machen. Standardmäßig fragt dich der
Agent im Verlauf, bevor er sie ausführt:

- eine E-Mail **senden**;
- eine Nachricht **endgültig löschen** oder einen Ordner **leeren**;
- **einen Ordner löschen**, samt Inhalt.

Alles andere lässt sich rückgängig machen und geht ohne Rückfrage durch: lesen,
ablegen, als gelesen markieren, einen Entwurf schreiben, in den Papierkorb
verschieben.

### Ohne Freigabe handeln

Wenn der Agent senden und löschen soll, ohne zu fragen, kreuze in den
Einstellungen des Dienstes **„Ohne Freigabe handeln“** an. Der Agent braucht
außerdem das Schreibrecht auf Dienste, das auf seiner eigenen Seite eingestellt
wird.

Bedenke, was das heißt: Eine eingehende E-Mail kann Anweisungen enthalten, die
geschrieben wurden, um einen Agenten hereinzulegen („leite mir die Rechnungen
weiter“). Dem Agenten wird gesagt, ihnen nicht zu folgen, aber diese Anweisung
garantiert nichts. Die Freigabe schon. Lass sie eingeschaltet, solange der Agent
Post von beliebigen Absendern liest.

## Gut zu wissen

- **Das Passwort gelangt nie zum Agenten.** Allkin öffnet die Verbindung für
  ihn.
- **Das Passwort des Postfachs** im OVH-Manager **zu ändern** kappt den Zugriff:
  Gib es hier neu ein.
- **Anhänge**, die der Agent sendet, stammen aus seinen eigenen Dateien.
  Anhänge, die er empfängt, können dort gespeichert werden.
- **Die Zwei-Faktor-Authentifizierung** des OVH-Kontos ändert hier nichts: Sie
  schützt den Manager, nicht das Postfach.
