# Fly.io

Apps and machines through the Machines API: state, start and stop, creation, volumes.

## The token

A token from the dashboard (**Tokens → Create**: an org token, or a deploy token limited to one app), or `fly tokens create org`.

## Good to know

Creating a machine costs money as long as it exists: it asks for your confirmation, like deleting. Logs are not in this API.
