# YouTube

Your channel: videos, playlists, comments, subscriptions, search.

## The application

The same Google Cloud application as every other Google service of Allkin: **<https://console.cloud.google.com>** → a project → **APIs and services → Credentials → Create credentials → OAuth client ID**, type **Web application**, with the redirect URI shown on the "Service" tab copied character for character. Enter its Client ID and Client Secret here, tick the scopes, **Connect**.

Enable **YouTube Data API v3** under **Library** of the same project: a scope on a disabled API gives a refusal that does not say why.

While the consent screen is in *Testing*, only test users can authorise and the token dies after seven days: move it to *Production* for a lasting connection. See the help of "Google (all APIs)" for the details.

## Good to know

The daily quota is 10 000 units and a search costs 100: the agent is told to search sparingly. Editing a video and deleting ask for your confirmation. Uploads are not offered through this relay.
