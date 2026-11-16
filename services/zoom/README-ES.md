# Zoom

Reuniones, grabaciones, usuarios e informes de tu cuenta Zoom.

## La aplicación

Una aplicación **Server-to-Server OAuth**: **<https://marketplace.zoom.us>** → **Develop → Build App → Server-to-Server OAuth**. Su página *App Credentials* da tres valores: **Account ID**, **Client ID**, **Client Secret**. Añade los ámbitos que necesita el agente (meeting:read:admin, meeting:write:admin, recording:read:admin…) y activa la aplicación. Introduce los tres valores; *Probar* obtiene un token.

## Conviene saber

El token dura una hora y Allkin lo renueva. Cancelar una reunión o eliminar una grabación pide tu confirmación.
