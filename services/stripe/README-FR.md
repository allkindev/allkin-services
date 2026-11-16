# Stripe

Paiements, clients, factures, abonnements, remboursements, liens de paiement.

## La clé

**<https://dashboard.stripe.com/apikeys>**. Préfère une **clé restreinte** avec les seules permissions dont l'agent a besoin, et commence par la clé du **mode test** (`sk_test_…`) : rien de réel ne bouge avec elle.

## Bon à savoir

Tout ce qui bouge de l'argent — remboursements, débits, virements, paiement d'une facture, abonnements — demande ta confirmation, comme supprimer. Les montants sont dans la plus petite unité (centimes).
