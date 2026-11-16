# GitHub

Repositories, issues, pull requests.

## Creating the token

**Settings** → **Developer settings** → **Personal access tokens**.

Fine-grained tokens are preferable: they can be limited to chosen repositories,
where a classic token applies to your whole account.

Give it **the fewest scopes possible**. An agent reading issues does not need to
write code; an agent opening pull requests does not need to administer the
organisation.

## Good to know

The token acts as you: whatever the agent writes will appear under your name and
avatar. To tell its work from yours, create a machine account and take the token
from there.
