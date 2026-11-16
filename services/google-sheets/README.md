# Google Sheets

Spreadsheets: read ranges, write, append rows, add sheets.

## The application

The same Google Cloud application as every other Google service of Allkin: **<https://console.cloud.google.com>** → a project → **APIs and services → Credentials → Create credentials → OAuth client ID**, type **Web application**, with the redirect URI shown on the "Service" tab copied character for character. Enter its Client ID and Client Secret here, tick the scopes, **Connect**.

Enable **Google Sheets API** under **Library** of the same project: a scope on a disabled API gives a refusal that does not say why.

While the consent screen is in *Testing*, only test users can authorise and the token dies after seven days: move it to *Production* for a lasting connection. See the help of "Google (all APIs)" for the details.

## Good to know

The connection test cannot call Sheets without a spreadsheet: the token is checked at "Connect" instead. Clearing a range asks for your confirmation. Finding a spreadsheet is Google Drive's job.
