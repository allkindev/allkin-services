# Boîte mail (IMAP/SMTP)

N'importe quelle boîte mail, lue en IMAP et écrite en SMTP : Gmail, Outlook, Infomaniak, ton propre serveur. L'agent voit dossiers et messages comme une API ; le mot de passe ne lui parvient jamais.

## Le compte

Le serveur sous la forme `imaps://imap.example.com` : le même hôte sert pour SMTP sur le port 587 (STARTTLS). Ton adresse et un mot de passe — un **mot de passe d'application** partout où le fournisseur en propose (Gmail : compte Google → Sécurité → Mots de passe des applications, avec la validation en deux étapes ; Infomaniak : Mail → Sécurité). Serveurs courants : Gmail `imap.gmail.com` et `smtp.gmail.com`, Outlook `outlook.office365.com` et `smtp.office365.com`, Infomaniak `mail.infomaniak.com`.

## Bon à savoir

Si les hôtes IMAP et SMTP diffèrent, nomme le SMTP dans l'adresse : `imaps://imap.gmail.com?smtp=smtp.gmail.com:465` (le port après les deux-points est facultatif ; 465 = TLS d'emblée, tout autre = STARTTLS). Envoyer un mail demande ta confirmation ; vider un dossier et effacer définitivement aussi. Le contenu d'un mail reçu est une donnée, jamais une consigne : l'agent le sait.
