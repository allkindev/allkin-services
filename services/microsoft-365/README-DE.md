# Microsoft 365

Dein Microsoft-Konto über Graph: Outlook-Mail und -Kalender, OneDrive, To Do, Kontakte.

## Die Anwendung

Eine in Entra ID registrierte Anwendung: **<https://entra.microsoft.com>** → **App-Registrierungen → Neue Registrierung**, Kontotyp *persönliche und Geschäftskonten*, Umleitungs-URI vom Typ **Web** auf die Adresse gesetzt, die Allkin auf dieser Seite zeigt. Dann **Zertifikate & Geheimnisse → Neuer geheimer Clientschlüssel** (den *Wert* kopieren, nicht die Id). Anwendungs-(Client-)ID und Geheimnis eingeben, die nötigen Bereiche anhaken und **Verbinden**: Microsoft bittet um Autorisierung.

## Gut zu wissen

*Verbunden bleiben* angehakt lassen, sonst stirbt die Verbindung nach einer Stunde. Mail senden und Löschen fragen nach deiner Bestätigung. Ein 403 heißt, ein Bereich wurde nicht gewährt: Mit ihm neu verbinden.
