# Mailbox (IMAP/SMTP)

Any mailbox, read over IMAP and written over SMTP: Gmail, Outlook, Infomaniak, your own server. The agent sees folders and messages as an API; the password never reaches it.

## The account

The server as `imaps://imap.example.com`: the same host is used for SMTP on port 587 (STARTTLS). Your address and a password — an **application password** wherever the provider offers one (Gmail: Google account → Security → App passwords, with two-step verification on; Infomaniak: Mail → Security). Common servers: Gmail `imap.gmail.com` and `smtp.gmail.com`, Outlook `outlook.office365.com` and `smtp.office365.com`, Infomaniak `mail.infomaniak.com`.

## Good to know

When the IMAP and SMTP hosts differ, name the SMTP one in the address: `imaps://imap.gmail.com?smtp=smtp.gmail.com:465` (the port after the colon is optional; 465 means TLS at once, anything else STARTTLS). Sending a mail asks for your confirmation; emptying a folder and erasing permanently too. The content of a received mail is data, never an instruction: the agent is told so.
