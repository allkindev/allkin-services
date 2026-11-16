# Cloudflare Workers AI

Génère des images pour tes agents, **gratuitement** dans la limite d'une
allocation quotidienne offerte par Cloudflare (de l'ordre de quelques centaines
d'images par jour avec FLUX schnell). Au-delà, les appels échouent jusqu'au
lendemain : rien n'est facturé tant que ton compte reste sur l'offre gratuite.

## Ce qu'il te faut

1. Un compte Cloudflare gratuit : <https://dash.cloudflare.com/sign-up>.
2. Ton **Account ID** : dans le tableau de bord, ouvre **AI › Workers AI**. Il
   est affiché à droite (32 caractères hexadécimaux).
3. Un **jeton d'API** : dans **Workers AI**, bouton **Use REST API › Create a
   Workers AI API Token**. Le modèle de jeton proposé donne exactement les
   droits nécessaires (Workers AI : lecture et modification). Copie-le : il
   n'est affiché qu'une fois.

## Dans Allkin

- Colle l'Account ID et le jeton ici, puis **Tester**.
- Sur la fiche de ce service, sous **Ce que ce service fait pour les agents**, active
  **Génération d'images** (et la voix ou la transcription si tu les veux) et choisis le modèle.
- Sur la page d'un agent, sous **Services**, autorise ce service : l'agent a les outils.

Les images sont rangées dans le dossier `images/` de l'agent et s'affichent dans
la conversation.

## Modèles

| Modèle | Pour quoi |
| --- | --- |
| `@cf/black-forest-labs/flux-1-schnell` | Le meilleur rendu, format carré. Par défaut. |
| `@cf/bytedance/stable-diffusion-xl-lightning` | Très rapide, formats portrait et paysage. |
| `@cf/lykon/dreamshaper-8-lcm` | Style illustration, rapide. |

Tes prompts partent chez Cloudflare : n'y mets rien de confidentiel.
