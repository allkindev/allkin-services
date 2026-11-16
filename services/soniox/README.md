# Soniox

Speech to text, in real time and on recorded files, with the speakers told apart. Billed by the hour of audio.

## The key

**<https://console.soniox.com>** → a project → **API Keys → Create API key**.

## Good to know

A Soniox project lives in **one region**, and its key only works there. The address filled in is the one of the United States; for a project created in another region, replace it with `https://api.eu.soniox.com` (European Union), `https://api.jp.soniox.com` (Japan) or `https://api.in.soniox.com` (India). A key used against the wrong region is refused like a wrong key.

Listening to a microphone goes through the **Recordr** plugin: choose this service in its settings. The audio then goes from the browser straight to Soniox, with a key that lives two minutes; the real key stays in Allkin.

An agent that is granted this service can transcribe a recording reachable by URL. A file on the agent's disk cannot be sent through this relay.
