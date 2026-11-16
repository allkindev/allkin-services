# Transmission

Torrents a través del RPC del demonio: listar, añadir, iniciar, detener, quitar.

## La cuenta

El usuario y la contraseña de la interfaz web (`rpc-username` y `rpc-password`
en `settings.json`, o los `USER`/`PASS` del contenedor). La dirección es la de
la interfaz web, sin `/transmission`.

## Conviene saber

Transmission protege su RPC con un token de sesión: Allkin lo obtiene y lo
reenvía por sí solo. Quitar un torrent con sus datos pide al agente que lo
compruebe contigo antes.
