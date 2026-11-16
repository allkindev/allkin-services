# Matrix

Salons et messages d'un serveur Matrix (Synapse, Conduit, Dendrite…).

## Le jeton

Un jeton d'accès du compte au nom duquel l'agent parlera — de préférence un
compte de bot dédié. Dans Element : **Paramètres → Aide et à propos →
Avancé → Jeton d'accès**. Ou en se connectant par l'API :

```
POST https://<serveur>/_matrix/client/v3/login
{"type":"m.login.password","identifier":{"type":"m.id.user","user":"bot"},"password":"…"}
```

L'adresse est celle du serveur (`https://matrix.example.org`), pas celle
d'Element.

## Bon à savoir

Les salons chiffrés ne se lisent pas par ce chemin : l'agent ne peut utiliser
que des salons non chiffrés. Quitter un salon et retirer un message demandent
ta confirmation.
