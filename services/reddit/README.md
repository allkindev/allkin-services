# Reddit

Subreddits, posts and comments, read through a registered application.

## The application

**<https://www.reddit.com/prefs/apps>** → **create another app** → type
**script**, any name, redirect URI `http://localhost`. The id is the short
string under the app name; the secret is next to it.

Enter them as client id and client secret. "Test" asks Reddit for a token and
reads a public subreddit: that is the whole connection.

## Good to know

An application token reads public content only: no posting, no voting, no
private messages. Reddit allows about sixty calls a minute per application.
