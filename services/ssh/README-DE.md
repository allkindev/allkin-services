# Rechner über SSH

Ein Server, ein NAS, ein Raspberry Pi — jeder Rechner mit einem SSH-Server. Die Agenten, denen du diesen Dienst gibst, führen dort Befehle aus, lesen und schreiben seine Dateien und sehen nie das Passwort oder den Schlüssel: sie bleiben auf diesem Server, außerhalb der Unterhaltung, außer Reichweite des Modells, außerhalb des Protokolls.

## Die Verbindung

**Rechner**: sein Name oder seine IP-Adresse, mit dem Port, falls er nicht 22 ist (`server.example.com:2222`). **Konto**: der Benutzer, mit dem sich die Agenten anmelden; ihre Rechte auf dem Rechner sind seine — ein eigenes Konto mit nur dem `sudo`, das es braucht, ist die sichere Wahl.

Dann eines von beiden:

- **Ein Schlüssel** (empfohlen). Drücke **Paar erzeugen**: der öffentliche Schlüssel erscheint darunter, um ihn in `~/.ssh/authorized_keys` des Kontos auf dem Rechner einzutragen — zum Beispiel dort `echo 'ssh-ed25519 AAAA… allkin@…' >> ~/.ssh/authorized_keys`. Du kannst auch einen eigenen privaten Schlüssel unverschlüsselt einfügen.
- **Ein Passwort**: das des Kontos, so wie du es eintippen würdest.

## Der Schlüssel des Rechners

Der erste Test übernimmt den Schlüssel, mit dem sich der Rechner ausweist, und zeigt seinen Fingerabdruck: vergleiche ihn, wenn du kannst, mit `ssh-keygen -lf /etc/ssh/ssh_host_ed25519_key.pub` auf dem Rechner. Danach wird ein Rechner mit einem anderen Schlüssel abgelehnt — neu installiert, oder ein anderer Rechner antwortet unter seiner Adresse. Wenn du weißt, warum er sich geändert hat: **Diesem Schlüssel vertrauen** auf dieser Seite.

## Was die Agenten tun

Drei Werkzeuge: ein Befehl, das Lesen einer Datei, das Schreiben einer Datei. Jeder Aufruf zeigt dir eine Karte im Verlauf — der Rechner, der Befehl, die Erklärung des Agenten — und läuft erst nach deiner Freigabe: einmal, für den Rest der Unterhaltung auf diesem Rechner, oder immer, über ein Muster nur für diesen Rechner. **Ohne Freigabe handeln** hebt die Karte für alle Agenten auf, auch in einer Aktion oder Delegation, ohne dass jemand sie sieht: kreuze es nur für einen Rechner an, den du ganz anvertrauen würdest. Die in Einstellungen › Agenten verbotenen Befehle bleiben hier verboten. Jeder Aufruf hinterlässt seine Zeile im Protokoll, Kategorie Computer.
