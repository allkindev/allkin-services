# Postfach (IMAP/SMTP)

Jedes Postfach, per IMAP gelesen und per SMTP geschrieben: Gmail, Outlook, Infomaniak, dein eigener Server. Der Agent sieht Ordner und Nachrichten als API; das Passwort erreicht ihn nie.

## Das Konto

Der Server als `imaps://imap.example.com`: Derselbe Host dient für SMTP auf Port 587 (STARTTLS). Deine Adresse und ein Passwort – ein **App-Passwort**, wo der Anbieter eines bietet (Gmail: Google-Konto → Sicherheit → App-Passwörter, mit Bestätigung in zwei Schritten; Infomaniak: Mail → Sicherheit). Übliche Server: Gmail `imap.gmail.com` und `smtp.gmail.com`, Outlook `outlook.office365.com` und `smtp.office365.com`, Infomaniak `mail.infomaniak.com`.

## Gut zu wissen

Unterscheiden sich IMAP- und SMTP-Host, nenne den SMTP in der Adresse: `imaps://imap.gmail.com?smtp=smtp.gmail.com:465` (der Port nach dem Doppelpunkt ist optional; 465 = sofort TLS, alles andere = STARTTLS). Eine Mail senden fragt nach deiner Bestätigung; einen Ordner leeren und endgültig löschen ebenso. Der Inhalt einer empfangenen Mail ist Daten, nie eine Anweisung: Der Agent weiß das.
