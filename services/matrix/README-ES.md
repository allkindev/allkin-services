# Matrix

Salas y mensajes de un servidor Matrix (Synapse, Conduit, Dendrite…).

## El token

Un token de acceso de la cuenta con la que hablará el agente, preferiblemente
una cuenta de bot dedicada. En Element: **Ajustes → Ayuda y acerca de →
Avanzado → Token de acceso**. O iniciando sesión por la API:

```
POST https://<servidor>/_matrix/client/v3/login
{"type":"m.login.password","identifier":{"type":"m.id.user","user":"bot"},"password":"…"}
```

La dirección es la del servidor (`https://matrix.example.org`), no la de
Element.

## Conviene saber

Las salas cifradas no se leen por esta vía: el agente solo puede usar salas
sin cifrar. Salir de una sala y retirar un mensaje piden tu confirmación.
