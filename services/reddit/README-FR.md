# Reddit

Subreddits, publications et commentaires, en lecture, par une application
enregistrée.

## L'application

**<https://www.reddit.com/prefs/apps>** → **create another app** → type
**script**, un nom quelconque, redirect URI `http://localhost`. L'identifiant
est la courte chaîne sous le nom de l'application ; le secret est à côté.

Saisis-les comme identifiant client et secret client. « Tester » demande un
jeton à Reddit et lit un subreddit public : c'est toute la connexion.

## Bon à savoir

Un jeton d'application ne lit que le contenu public : ni publication, ni vote,
ni message privé. Reddit autorise environ soixante appels par minute par
application.
