# Cloudflare Workers AI

Generates images for your agents, **for free** within a daily allowance granted
by Cloudflare (in the order of a few hundred images a day with FLUX schnell).
Beyond it, calls fail until the next day: nothing is billed as long as your
account stays on the free plan.

## What you need

1. A free Cloudflare account: <https://dash.cloudflare.com/sign-up>.
2. Your **Account ID**: in the dashboard, open **AI › Workers AI**. It is shown
   on the right (32 hexadecimal characters).
3. An **API token**: in **Workers AI**, button **Use REST API › Create a
   Workers AI API Token**. The token template it proposes gives exactly the
   rights needed (Workers AI: read and edit). Copy it: it is shown only once.

## In Allkin

- Paste the Account ID and the token here, then **Test**.
- On this service's page, under **What this service does for the agents**, switch on
  **Image generation** (and voice or transcription if you want them) and pick the model.
- On an agent's page, under **Services**, allow this service: the agent gets the tools.

Images are stored in the agent's `images/` folder and shown in the
conversation.

## Models

| Model | What for |
| --- | --- |
| `@cf/black-forest-labs/flux-1-schnell` | The best rendering, square format. The default. |
| `@cf/bytedance/stable-diffusion-xl-lightning` | Very fast, portrait and landscape formats. |
| `@cf/lykon/dreamshaper-8-lcm` | Illustration style, fast. |

Your prompts go to Cloudflare: put nothing confidential in them.
