# Home Assistant

Gives an agent the state of your home, and the means to act on it.

## The base URL

Your Home Assistant address, **including the port**, and **without a trailing
`/api`**:

```
http://192.168.1.20:8123         ✅
http://192.168.1.20:8123/api     ❌
```

## The token

Click **your name at the bottom of the sidebar** → **Security** tab → at the
very bottom, **"Create token"**. It is shown only once.

This is a long-lived token tied to your account: it has exactly your rights.
Home Assistant cannot issue a narrower one — if you want to bound what an agent
can do, create a dedicated Home Assistant user and take the token from that
account.

## Useful calls

| Call | What it does |
| --- | --- |
| `GET /api/states` | the state of everything |
| `GET /api/states/light.living` | one entity's state |
| `POST /api/services/light/turn_on` | turns on, with `{"entity_id": "light.living"}` |

`GET /api/states` often returns several hundred entities. The agent knows how to
extract only what it needs — there is no need to make it read everything.

## What actually helps an agent

The **"Instructions for agents"** field on the Service tab. No generic
documentation can know that your living room is `light.main_living`: that is
often the only missing piece for getting it right the first time.
