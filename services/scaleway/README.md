# Scaleway

Instances, object storage, serverless, managed databases, billing of Scaleway.

## The key

**IAM → API keys → Generate an API key**, for an application or a user, with a default project. Enter the **secret key** (the access key is not needed).

## Good to know

Most calls name a zone or region in their path; the agent knows the usual ones. Creating an instance and deleting ask for your confirmation. Object storage itself (S3) needs its own keys.
