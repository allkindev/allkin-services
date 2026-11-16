# OpenWeather

Météo courante et prévisions.

## La clé

**<https://openweathermap.org>** → ton compte → **API keys**.

Une clé neuve met **jusqu'à deux heures** à devenir active. Un `401` juste après
l'inscription n'est donc pas une erreur de saisie : c'est trop tôt.

## Bon à savoir

Le palier gratuit couvre la météo courante et les prévisions à cinq jours, dans
la limite de soixante appels par minute. Les API « One Call » et historiques
demandent un abonnement — un agent qui reçoit un `401` sur celles-là a une clé
valide mais pas le bon plan.
