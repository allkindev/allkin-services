# SearXNG

La recherche web de vos agents par votre propre SearXNG : il interroge
plusieurs moteurs de recherche à la fois, depuis votre machine, sans clé ni
quota.

## Ce qu'il faut

L'**intégration SearXNG** d'Allkin (Intégrations → Ajouter → SearXNG),
installée, ses droits accordés et son service démarré. Elle installe et lance
SearXNG sur la machine toute seule ; ce service est le chemin par lequel les
agents l'atteignent.

## L'adresse

`http://127.0.0.1:9350` — le port est le **Port local** des réglages de
l'intégration (9350 si vous ne l'avez pas changé). Il n'y a aucune clé à coller.

## Le donner à un agent

Sur la page de l'agent, dans ses services, cochez **SearXNG**. L'agent cherche
alors sur le web, dans les actualités, les images et les vidéos par ce service.

## Quand le test échoue

- **Aucune réponse** : l'intégration n'est pas démarrée — ouvrez sa page,
  accordez ses droits et démarrez-la.
- **« not-ready »** : SearXNG s'installe encore (quelques minutes la première
  fois) ou démarre. Patientez, puis testez de nouveau.
- **Un mauvais port** : l'adresse doit porter le port des réglages de
  l'intégration.

## Bon à savoir

Les moteurs de recherche refusent parfois les requêtes d'un serveur pendant un
moment (un CAPTCHA, un délai dépassé) : une recherche revient alors avec moins
de résultats, et dit quels moteurs n'ont pas répondu. Ce service ne s'adresse
pas à un SearXNG installé autrement : il parle à l'intégration, qui répond sous
une forme plus courte que l'API de SearXNG.
