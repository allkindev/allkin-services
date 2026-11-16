# Transmission

Torrents par le RPC du démon : lister, ajouter, démarrer, arrêter, retirer.

## Le compte

L'identifiant et le mot de passe de l'interface web (`rpc-username` et
`rpc-password` dans `settings.json`, ou les `USER`/`PASS` du conteneur).
L'adresse est celle de l'interface web, sans `/transmission`.

## Bon à savoir

Transmission protège son RPC par un jeton de session : Allkin le récupère et
le renvoie tout seul. Retirer un torrent avec ses données demande à l'agent de
vérifier avec toi d'abord.
