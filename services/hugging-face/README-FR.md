# Hugging Face

Le Hub : chercher des modèles, jeux de données et spaces, lire leurs fiches et fichiers.

## La clé

**<https://huggingface.co/settings/tokens>** → **Create new token**, lecture seule suffit pour le Hub.

## Bon à savoir

L'inférence (faire tourner un modèle) vit sur un autre hôte que ce service n'atteint pas : prends OpenAI, Mistral ou OpenRouter pour ça, ou l'entrée API générique pointée sur `https://router.huggingface.co` avec le même jeton.
