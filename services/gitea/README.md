# Gitea / Forgejo

Repositories, issues, pull requests, releases — on Gitea or Forgejo, same API.

## The token

**Settings → Applications → Generate new token**, with the scopes the agent
needs (`read:repository`, `write:issue`…). The address is the root of your
instance.

## Good to know

Deleting a repository asks for your confirmation and says what it means. The
API mirrors GitHub's: an agent used to one finds its way in the other.
