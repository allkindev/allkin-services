# qBittorrent

Gives an agent access to your BitTorrent client: list torrents, watch transfer
rates, pause, add, delete.

## What you need

Two things, both from qBittorrent itself:

| Field | Where to find it |
| --- | --- |
| Base URL | The Web UI address, **followed by `/api/v2`** |
| Username, password | Tools → Options → Web UI |

## The base URL

This is the one thing people get wrong. The address must point at the API, not
at the page:

```
http://127.0.0.1:8080/api/v2      ✅
http://127.0.0.1:8080             ❌ every call returns 404
```

If qBittorrent runs on another machine, replace `127.0.0.1` with its address,
and make sure "Web User Interface (Remote control)" is enabled in the options —
otherwise nothing is listening from outside.

## The localhost trap

qBittorrent enables **"Bypass authentication for clients on localhost"** by
default.

As a result, if Allkin runs on the same machine, the connection succeeds **even
with a wrong password**. The test turns green, and it is not lying — it only
proves the machine is right, not your credentials.

This does not break anything. But the day you move qBittorrent elsewhere, the
connection will fail all at once: the password had never been checked. Uncheck
the option if you want the test to mean something.

## What the agent may do, and what you approve

Reading and adjusting needs no approval: torrent list, transfer rates, pause,
resume, categories, priorities. All of it is one click away from being undone.

Five operations go through your approval, in the conversation:

- **adding a torrent** — takes disk space and bandwidth immediately
- **deleting** — with `deleteFiles=true`, the downloaded files leave the disk
- **moving a torrent's files**
- **changing the configuration** — preferences include the Web UI authentication
- **shutting qBittorrent down**

This is not an instruction given to the agent: the code intercepts the call. No
agent can opt out of it.

## Password and session

The password is used once, to open the session. What travels afterwards is a
cookie, renewed automatically, and revocable from qBittorrent without changing
the password. The agent sees neither.
