# Sentry

The errors of your applications: issues, their events and stack traces, releases, stats.

## The token

**Settings → Auth Tokens → Create New Token** (an organization token, scoped to what the agent needs: `event:read`, `project:read`, `event:write` to resolve). The address is `https://sentry.io`, or the root of your self-hosted Sentry.

## Good to know

An event with its stack trace is big: the agent reads the list of issues first. Deleting asks for your confirmation.
