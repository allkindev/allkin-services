# Zoom

Meetings, recordings, users and reports of your Zoom account.

## The application

A **Server-to-Server OAuth** app: **<https://marketplace.zoom.us>** → **Develop → Build App → Server-to-Server OAuth**. Its *App Credentials* page gives three values: **Account ID**, **Client ID**, **Client Secret**. Add the scopes the agent needs (meeting:read:admin, meeting:write:admin, recording:read:admin…) and activate the app. Enter the three values; *Test* fetches a token.

## Good to know

The token lives an hour and is renewed by Allkin. Cancelling a meeting or deleting a recording asks for your confirmation.
