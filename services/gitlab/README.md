# GitLab

Projects, issues, merge requests, pipelines and files — on gitlab.com or your own instance.

## The token

**Your avatar → Preferences → Access tokens → Add new token**, with the scopes the agent needs (`read_api` to read, `api` to write). The address is `https://gitlab.com`, or the root of your instance.

## Good to know

A project access token limits the agent to one project: the safer choice for a bot. Deleting a project asks for your confirmation and says what it means.
