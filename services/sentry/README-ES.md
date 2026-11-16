# Sentry

Los errores de tus aplicaciones: issues, sus eventos y trazas, versiones, estadísticas.

## El token

**Settings → Auth Tokens → Create New Token** (un token de organización, limitado a lo que necesita el agente: `event:read`, `project:read`, `event:write` para resolver). La dirección es `https://sentry.io`, o la raíz de tu Sentry autoalojado.

## Conviene saber

Un evento con su traza es voluminoso: el agente lee primero la lista de issues. Eliminar pide tu confirmación.
