# Sentry

Die Fehler deiner Anwendungen: Issues, ihre Ereignisse und Stacktraces, Releases, Statistiken.

## Das Token

**Settings → Auth Tokens → Create New Token** (ein Organisations-Token, beschränkt auf das, was der Agent braucht: `event:read`, `project:read`, `event:write` zum Lösen). Die Adresse ist `https://sentry.io` oder die Wurzel deines selbst gehosteten Sentry.

## Gut zu wissen

Ein Ereignis mit Stacktrace ist groß: Der Agent liest zuerst die Liste der Issues. Löschen fragt nach deiner Bestätigung.
