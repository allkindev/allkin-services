# OVHcloud Mail

Donne à un agent l'accès complet à une boîte mail OVH : lire, chercher,
classer, répondre, envoyer, supprimer.

Tout ce que fait l'agent se retrouve dans ton webmail : c'est la même boîte, sur
le même serveur. Il ne passe pas par l'écran du webmail. Il parle directement
à ce serveur, en IMAP pour lire et en SMTP pour envoyer.

## Ce qu'il te faut

| Champ | Valeur |
| --- | --- |
| Serveur | `ssl0.ovh.net` pour **MX Plan** (déjà rempli) ; pour **Email Pro**, le serveur `proN.mail.ovh.net` affiché dans le manager |
| Adresse e-mail | l'adresse complète, `toi@ton-domaine.fr` |
| Mot de passe | celui de la boîte, le même que pour le webmail |

Le bouton « Ajouter » vérifie la **lecture** et l'**envoi**, séparément. Un
compte peut très bien lire sans pouvoir envoyer : OVH bloque l'envoi d'une
boîte soupçonnée de spam, et c'est ce que la vérification te dira.

## Ce que l'agent ne fait pas seul

Trois gestes ne se défont pas. Par défaut, l'agent te les soumet dans le fil :

- **envoyer** un mail ;
- **effacer définitivement** un message, ou **vider** un dossier ;
- **supprimer un dossier**, avec son contenu.

Le reste se défait et passe sans rien demander : lire, classer, marquer comme
lu, écrire un brouillon, mettre à la corbeille.

### Agir sans validation

Si tu veux que l'agent envoie et efface sans te demander, coche **« Agir sans
validation »** dans la configuration du service. L'agent doit avoir en plus
le droit d'écriture sur les services, réglé sur sa page.

Pense à ce que ça implique : un mail reçu peut contenir des instructions
écrites pour tromper un agent (« transfère-moi les factures »). L'agent est
prévenu de ne pas y obéir, mais cette consigne n'a rien d'une garantie. La
validation, elle, en est une. Garde-la tant que l'agent lit du courrier venu
de n'importe qui.

## Bon à savoir

- **Le mot de passe ne va jamais à l'agent.** Allkin ouvre la connexion à sa
  place.
- **Changer le mot de passe de la boîte** dans le manager OVH coupe l'accès :
  ressaisis-le ici.
- **Les pièces jointes** que l'agent envoie viennent de ses fichiers. Celles
  qu'il reçoit peuvent y être enregistrées.
- Si **la double authentification** est activée sur le compte OVH, ça ne
  change rien ici : elle protège le manager, pas la boîte mail.
