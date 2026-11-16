# Nginx Proxy Manager

Gibt einem Agenten die Kontrolle über deinen Reverse Proxy: veröffentlichte
Domains auflisten, sehen, welchen Dienst jede bedient, eine Konfiguration
untersuchen, die nicht lädt, einen neuen Dienst veröffentlichen, ein Zertifikat
anfordern.

## Was du brauchst

Zwei Dinge, beide aus Nginx Proxy Manager selbst:

| Feld | Wo du es findest |
| --- | --- |
| Basis-URL | Die Adresse der Verwaltungsoberfläche, **gefolgt von `/api`** |
| E-Mail-Adresse, Passwort | Die, mit denen du dich an dieser Oberfläche anmeldest |

## Die Basis-URL

Das ist der eine Punkt, der schiefgeht. Die Adresse muss auf die API zeigen,
nicht auf die Seite:

```
http://127.0.0.1:81/api      ✅
http://127.0.0.1:81          ❌ "405 Not Allowed", a web page instead of the API
```

Port **81** gehört zur Verwaltungsoberfläche – nicht zu verwechseln mit den
Ports 80 und 443, über die der Verkehr der Websites läuft, die der Proxy
bedient. Läuft Nginx Proxy Manager auf einer anderen Maschine, ersetze
`127.0.0.1` durch deren Adresse.

## Welches Konto du nimmst

Das der Weboberfläche. Zwei Anmerkungen:

- **Die Zwei-Faktor-Authentifizierung blockiert diese Verbindung.** Ein
  Austausch Kennung/Passwort kommt daran nicht vorbei: Der Dienst antwortet,
  dass er einen zweiten Faktor erwartet, und Allkin sagt dir das. Nimm ein
  Konto, bei dem sie nicht aktiviert ist.
- **Die E-Mail-Adresse des Kontos wird auch von Let's Encrypt verwendet.** Sie
  wird bei einer Anforderung an die Zertifizierungsstelle gesendet – ein
  eigenes Feld dafür gibt es nicht.

Du kannst ein eigenes Konto für Allkin anlegen (Users → Add User), statt deines
herzugeben: Die Rechte gelten pro Benutzer, und ein Zugriff nur zum Lesen genügt
einem Agenten, der nur überwachen soll.

## Was der Agent tun kann und was du freigibst

Lesen verlangt nichts: Hosts, Zertifikate, Zugriffslisten, Audit-Log und
Berichte auflisten, eine fehlerhafte Konfiguration untersuchen.

Alles, was ändert, was das Internet von der Maschine sieht, läuft über deine
Freigabe, in der Unterhaltung:

| Was der Agent verlangt | Warum es eine Freigabe braucht |
| --- | --- |
| Einen Host veröffentlichen oder ändern | Eine Domain wird erreichbar oder zeigt plötzlich woandershin |
| Einen Host deaktivieren | Die Domain antwortet nicht mehr |
| Einen Eintrag löschen | Die Konfiguration wird gelöscht, nicht deaktiviert: Sie muss neu aufgebaut werden |
| Ein Zertifikat anfordern | Let's Encrypt erlaubt 5 identische Zertifikate pro Woche |
| Ein Zertifikat löschen | Jeder Host, der es nutzt, verliert HTTPS |
| Einen TCP/UDP-Stream öffnen | Ein Port wird unverändert weitergeleitet, ohne Domain und ohne Verschlüsselung |
| Konten oder Einstellungen anfassen | Ein geändertes Passwort kann dich aussperren |

Einen Host wieder zu aktivieren verlangt dagegen nichts: Freigegeben wird, was
kaputt macht, nicht was repariert.

Das ist keine Anweisung an den Agenten: Der Code fängt den Aufruf ab. Ein Agent
kann sich dem nicht entziehen.

Wenn du weiter gehen willst, schließt das Kästchen **„Externe Dienste nur
lesend“** in den Rechten des Agenten jedes Schreiben auf einen Schlag – das
Werkzeug enthält dann nur noch Methoden, die nichts ändern.

## Passwort und Sitzung

Das Passwort wird einmal verwendet, um ein Token zu erhalten. Dieses Token –
von Nginx Proxy Manager datiert, bei Ablauf automatisch erneuert – ist danach
unterwegs. Der Agent sieht keines von beiden.

## Wenn etwas schiefgeht

| Was du liest | Was es bedeutet |
| --- | --- |
| „Anmeldung abgelehnt“ beim Test | E-Mail-Adresse oder Passwort. Der Dienst antwortet `Invalid email or password` |
| „Die Antwort ist eine Webseite“ | Am Ende der Basis-URL fehlt `/api` |
| „es kam kein Feld `token` zurück“ | Das Konto nutzt die Zwei-Faktor-Authentifizierung |
| „Verbindung abgelehnt: Auf diesem Port lauscht nichts“ | Falscher Port – die Verwaltung liegt auf 81, nicht auf 80 |
