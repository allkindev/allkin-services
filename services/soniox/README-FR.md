# Soniox

Transcription de la parole, en direct et sur des fichiers enregistrés, avec séparation des interlocuteurs. Facturé à l'heure d'audio.

## La clé

**<https://console.soniox.com>** → un projet → **API Keys → Create API key**.

## Bon à savoir

Un projet Soniox vit dans **une région**, et sa clé ne marche que là. L'adresse préremplie est celle des États-Unis ; pour un projet créé dans une autre région, remplacez-la par `https://api.eu.soniox.com` (Union européenne), `https://api.jp.soniox.com` (Japon) ou `https://api.in.soniox.com` (Inde). Une clé utilisée contre la mauvaise région est refusée comme une clé fausse.

L'écoute d'un micro passe par le plugin **Recordr** : choisissez ce service dans ses réglages. L'audio part alors du navigateur directement chez Soniox, avec une clé qui vit deux minutes ; la vraie clé reste dans Allkin.

Un agent à qui ce service est accordé peut transcrire un enregistrement accessible par URL. Un fichier présent sur le disque de l'agent ne peut pas être envoyé par ce relais.
