# SearXNG

Web search for your agents through your own SearXNG: it asks several search
engines at once, from your machine, with no key and no quota.

## What it needs

The **SearXNG integration** of Allkin (Integrations → Add → SearXNG), installed,
its rights granted and its service started. It installs and runs SearXNG on the
machine by itself; this service is how agents reach it.

## The address

`http://127.0.0.1:9350` — the port is the **Local port** of the integration's
settings (9350 unless you changed it). There is no key to paste.

## Giving it to an agent

On the agent's page, under its services, tick **SearXNG**. The agent then
searches the web, the news, images and videos through it.

## When the test fails

- **No answer**: the integration is not started — open its page, grant its
  rights and start it.
- **"not-ready"**: SearXNG is still installing (a few minutes the first time)
  or starting. Wait, then test again.
- **A wrong port**: the address must carry the port of the integration's
  settings.

## Good to know

Search engines sometimes refuse a server's requests for a while (a CAPTCHA, a
timeout): a search then comes back with fewer results, and says which engines
did not answer. This service does not address a SearXNG installed otherwise:
it speaks to the integration, which answers in a shorter form than SearXNG's
own API.
