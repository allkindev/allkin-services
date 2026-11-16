# Jellyfin

Your media library: libraries, films, series, what is currently playing.

## The key

**Dashboard** → **Advanced** → **API keys** → **+**.

## The base URL

Your server's address, as you would open it in a browser:

```
https://media.example.com        ✅
http://192.168.1.30:8096         ✅
```

No trailing slash — Allkin strips it anyway, but it is worth knowing: that slash
is what produces `//` and 404s when you paste the address from the browser bar.

## Good to know

A Jellyfin API key has administrator rights: it sees every library and every
user. There is no restricted key.
