# Paperless-ngx

Tes documents : recherche plein texte, étiquettes, correspondants, types.

## Le jeton

**Profil (en haut à droite) → Jeton d'authentification API → générer**. Ou
sur la machine : `manage.py drf_create_token <utilisateur>`. L'adresse est
celle de l'interface web.

## Bon à savoir

Les chemins finissent par une barre, l'API est paginée (25 par défaut).
Supprimer un document demande ta confirmation ; la corbeille le garde un temps
de toute façon.
