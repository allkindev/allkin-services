# Paperless-ngx

Your documents: full-text search, tags, correspondents, document types.

## The token

**Profile (top right) → API Auth Token → generate**. Or on the machine:
`manage.py drf_create_token <user>`. The address is the one of the web
interface.

## Good to know

Paths end with a slash, the API is paginated (25 by default). Deleting a
document asks for your confirmation; the bin keeps it for a while anyway.
