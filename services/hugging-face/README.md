# Hugging Face

The Hub: search models, datasets and spaces, read their cards and files.

## The key

**<https://huggingface.co/settings/tokens>** → **Create new token**, read-only is enough for the Hub.

## Good to know

Inference (running a model) lives on another host that this service does not reach: use OpenAI, Mistral or OpenRouter for that, or the generic API entry pointed at `https://router.huggingface.co` with the same token.
