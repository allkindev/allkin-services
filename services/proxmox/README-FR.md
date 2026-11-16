# Proxmox VE

Machines virtuelles, conteneurs, nœuds, stockage, tâches.

## Le jeton

**Datacenter → Permissions → API Tokens → Add** : choisis l'utilisateur, donne
un identifiant au jeton et laisse **Privilege Separation** coché pour que ses
droits soient réglés à part. Puis **Permissions → Add → API Token Permission**
sur les chemins qu'il peut toucher (`/` avec `PVEAuditor` pour lire,
`PVEVMAdmin` pour agir sur les VM).

Saisis la clé sous la forme `utilisateur@realm!jeton=secret`, d'un bloc,
telle que Proxmox l'affiche une seule fois. L'adresse est `https://hôte:8006`.

## Bon à savoir

Proxmox est livré avec un certificat auto-signé : Allkin le refuse. Pose un
vrai certificat sur le nœud, ou passe par un reverse proxy qui en a un.
Arrêter, redémarrer et supprimer demandent ta confirmation.
