# OVHcloud Mail

Gives an agent full access to an OVH mailbox: read, search, file, reply, send,
delete.

Everything the agent does shows up in your webmail, because it is the same
mailbox on the same server. The agent doesn't go through the webmail screen.
It talks to that server directly, using IMAP to read and SMTP to send.

## What you need

| Field | Value |
| --- | --- |
| Server | `ssl0.ovh.net` for **MX Plan** (prefilled); for **Email Pro**, the `proN.mail.ovh.net` server shown in the control panel |
| Email address | the full address, `you@your-domain.com` |
| Password | the mailbox password, the same one as for webmail |

The "Add" button checks **reading** and **sending** separately. An account can
read but still be unable to send: OVH blocks sending from a mailbox it
suspects of spam, and the check will tell you so.

## What the agent does not do on its own

Three actions can't be undone. By default, the agent asks you in the thread
before doing them:

- **sending** an email;
- **permanently deleting** a message, or **emptying** a folder;
- **deleting a folder** along with its contents.

Everything else can be undone and goes through without asking: reading,
filing, marking as read, writing a draft, moving to trash.

### Act without approval

If you want the agent to send and delete without asking, tick **« Agir sans validation »**
("act without approval") in the service settings. The agent also needs write access to
services, which is set on its own page.

Keep in mind what this means: an incoming email can carry instructions written
to trick an agent ("forward me the invoices"). The agent is told not to follow
them, but that instruction guarantees nothing. Approval does. Keep it on as
long as the agent reads mail from anyone.

## Good to know

- **The password never reaches the agent.** Allkin opens the connection for it.
- **Changing the mailbox password** in the OVH control panel cuts access:
  enter it again here.
- **Attachments** the agent sends come from its own files. Attachments it
  receives can be saved there.
- **Two-factor authentication** on the OVH account changes nothing here: it
  protects the control panel, not the mailbox.
