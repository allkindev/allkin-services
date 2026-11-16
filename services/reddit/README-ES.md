# Reddit

Subreddits, publicaciones y comentarios, en lectura, mediante una aplicación
registrada.

## La aplicación

**<https://www.reddit.com/prefs/apps>** → **create another app** → tipo
**script**, cualquier nombre, redirect URI `http://localhost`. El identificador
es la cadena corta bajo el nombre de la aplicación; el secreto está al lado.

Introdúcelos como identificador de cliente y secreto de cliente. «Probar» pide
un token a Reddit y lee un subreddit público: esa es toda la conexión.

## Conviene saber

Un token de aplicación solo lee contenido público: ni publicar, ni votar, ni
mensajes privados. Reddit permite unas sesenta llamadas por minuto por
aplicación.
