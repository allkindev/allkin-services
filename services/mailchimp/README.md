# Mailchimp

Audiences and their members, tags, campaigns and their reports.

## The key

**Account → Extras → API keys → Create A Key**. The key ends with `-us21` (or another code): that code is the **data centre** to enter; any name works as the login, the key is the password.

## Good to know

Sending a campaign goes to its whole audience at once: it asks for your confirmation, like deleting. Members are addressed by the MD5 of their lowercase email, which the agent computes.
