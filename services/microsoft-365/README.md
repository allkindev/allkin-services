# Microsoft 365

Your Microsoft account through Graph: Outlook mail and calendar, OneDrive, To Do, contacts.

## The application

An application registered in Entra ID: **<https://entra.microsoft.com>** → **App registrations → New registration**, account type *Personal and work accounts*, redirect URI of type **Web** set to the address Allkin shows on this page. Then **Certificates & secrets → New client secret** (copy its *value*, not its id). Enter the Application (client) ID and the secret, tick the scopes the agent needs, and **Connect**: Microsoft asks you to authorize.

## Good to know

Keep *Stay connected* ticked, or the connection dies after an hour. Sending mail and deleting ask for your confirmation. A 403 means a scope was not granted: reconnect with it.
