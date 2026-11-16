# Machine over SSH

A server, a NAS, a Raspberry Pi — any machine with an SSH server. The agents you grant this service run commands there, read and write its files, and never see the password or the key: they stay on this server, out of the conversation, out of the model's reach, out of the journal.

## The connection

**Machine**: its name or its IP address, with the port when it is not 22 (`server.example.com:2222`). **Account**: the user the agents sign in as; their rights on that machine are its rights — an account of its own, with only the `sudo` it needs, is the safe choice.

Then one of the two:

- **A key** (recommended). Press **Generate a pair**: the public key shows below, to add to `~/.ssh/authorized_keys` of the account on the machine — for instance `echo 'ssh-ed25519 AAAA… allkin@…' >> ~/.ssh/authorized_keys` there. You may also paste a private key of your own, unencrypted.
- **A password**: the account's, as you would type it.

## The key of the machine

The first test learns the key the machine introduces itself with, and shows its fingerprint: compare it, if you can, with `ssh-keygen -lf /etc/ssh/ssh_host_ed25519_key.pub` run on the machine. From then on, a machine that shows another key is refused — reinstalled, or another machine answering at its address. If you know why it changed, **Trust this key** on this page.

## What the agents do

Three tools: a command, a file read, a file written. Each call shows you a card in the thread — the machine, the command, the agent's explanation — and runs only once you approve it: once, for the rest of the conversation on this machine, or always, through a pattern saved for this machine only. **Act without approval** lifts the card for every agent, in an action or a delegation too, with nobody to see it: tick it only for a machine you would hand over whole. The commands forbidden in Settings › Agents stay forbidden here. Every call leaves its line in the journal, category Computers.
