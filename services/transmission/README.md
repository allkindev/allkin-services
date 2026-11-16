# Transmission

Torrents through the daemon's RPC: list, add, start, stop, remove.

## The account

The login and password of the web interface (`rpc-username` and
`rpc-password` in `settings.json`, or the `USER`/`PASS` of the container).
The address is the one of the web interface, without `/transmission`.

## Good to know

Transmission protects its RPC with a per-session token: Allkin fetches it and
sends it back by itself. Removing a torrent with its data asks the agent to
check with you first.
