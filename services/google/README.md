# Google

Gmail, Calendar, Drive, Sheets — through OAuth2, on behalf of your account.

## Creating the credentials

**<https://console.cloud.google.com>** → a project → **APIs and services** →
**Credentials** → **Create credentials** → **OAuth client ID** → type **Web
application**.

## The redirect URI

This is failure number one (`redirect_uri_mismatch`). The address shown on the
"Service" tab must be copied **exactly** into "Authorised redirect URIs",
character for character: protocol, port and the absence of a trailing slash all
count.

If you open Allkin under several addresses (domain name, IP address,
`localhost`), declare all of them: Google compares against the one you arrived
by, not a preferred one.

## Enabling the APIs

Each Google service is a separate API, enabled separately under **Library**:
Gmail API, Google Calendar API, Google Drive API, Google Sheets API. A scope
granted on a disabled API yields a refusal that does not say why.

## Scopes

Tick only what the agent needs. `gmail.readonly` is enough to read a mailbox;
only grant write access if the agent must actually send.

Changing the scopes of an already-connected service invalidates its token: you
will need to click "Connect" again.

## Consent screen

While the app is in **Testing** mode, only accounts added as "test users" can
authorise it, and the refresh token expires after seven days. Move the app to
**Production** for a lasting connection.
