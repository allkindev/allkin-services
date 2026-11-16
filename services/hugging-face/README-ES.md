# Hugging Face

El Hub: buscar modelos, conjuntos de datos y spaces, leer sus fichas y archivos.

## La clave

**<https://huggingface.co/settings/tokens>** → **Create new token**, solo lectura basta para el Hub.

## Conviene saber

La inferencia (ejecutar un modelo) vive en otro host al que este servicio no llega: usa OpenAI, Mistral u OpenRouter para eso, o la entrada API genérica apuntando a `https://router.huggingface.co` con el mismo token.
