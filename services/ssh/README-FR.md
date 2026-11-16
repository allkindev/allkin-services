# Machine en SSH

Un serveur, un NAS, un Raspberry Pi — toute machine qui a un serveur SSH. Les agents à qui vous donnez ce service y lancent des commandes, lisent et écrivent ses fichiers, et ne voient jamais le mot de passe ni la clé : ils restent sur ce serveur, hors de la conversation, hors de portée du modèle, hors du journal.

## La connexion

**Machine** : son nom ou son adresse IP, avec le port s'il n'est pas 22 (`serveur.example.com:2222`). **Compte** : l'utilisateur sous lequel les agents se connectent ; leurs droits sur la machine sont les siens — un compte à part, avec juste le `sudo` qu'il lui faut, est le choix sûr.

Puis l'un des deux :

- **Une clé** (recommandé). Appuyez sur **Générer une paire** : la clé publique s'affiche dessous, à ajouter au fichier `~/.ssh/authorized_keys` du compte sur la machine — par exemple `echo 'ssh-ed25519 AAAA… allkin@…' >> ~/.ssh/authorized_keys` là-bas. Vous pouvez aussi coller une clé privée à vous, non chiffrée.
- **Un mot de passe** : celui du compte, tel que vous le taperiez.

## La clé de la machine

Le premier test retient la clé avec laquelle la machine se présente, et affiche son empreinte : comparez-la si vous le pouvez avec `ssh-keygen -lf /etc/ssh/ssh_host_ed25519_key.pub` lancé sur la machine. Ensuite, une machine qui présente une autre clé est refusée — réinstallée, ou une autre machine qui répond à son adresse. Si vous savez pourquoi elle a changé, **Faites confiance à cette clé** depuis cette page.

## Ce que font les agents

Trois outils : une commande, la lecture d'un fichier, l'écriture d'un fichier. Chaque appel vous montre une carte dans le fil — la machine, la commande, l'explication de l'agent — et ne part qu'après votre accord : une fois, pour le reste de la conversation sur cette machine, ou toujours, par un motif retenu pour cette machine seulement. **Agir sans validation** lève la carte pour tous les agents, aussi dans une action ou une délégation, sans personne pour la voir : ne le cochez que pour une machine que vous confieriez entière. Les commandes interdites dans Paramètres › Agents restent interdites ici. Chaque appel laisse sa ligne dans le journal, catégorie Ordinateurs.
