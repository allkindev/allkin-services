# Google

Gmail, Calendar, Drive, Sheets: mediante OAuth2, en nombre de tu cuenta.

## Crear las credenciales

**<https://console.cloud.google.com>** → un proyecto → **APIs y servicios** →
**Credenciales** → **Crear credenciales** → **ID de cliente de OAuth** → tipo
**Aplicación web**.

## La URI de redirección

Es el fallo número uno (`redirect_uri_mismatch`). La dirección que aparece en la
pestaña «Servicio» debe copiarse **tal cual** en «URIs de redireccionamiento
autorizados», carácter por carácter: el protocolo, el puerto y la ausencia de
barra final cuentan.

Si abres Allkin con varias direcciones (nombre de dominio, dirección IP,
`localhost`), decláralas todas: Google compara con aquella por la que llegas, no
con una preferida.

## Activar las API

Cada servicio de Google es una API distinta, que se activa por separado en
**Biblioteca**: Gmail API, Google Calendar API, Google Drive API, Google Sheets
API. Un ámbito concedido sobre una API desactivada da un rechazo que no dice por
qué.

## Ámbitos

Marca solo lo que el agente necesita. `gmail.readonly` basta para leer un buzón;
concede la escritura solo si el agente tiene que enviar de verdad.

Cambiar los ámbitos de un servicio ya conectado invalida su token: tendrás que
pulsar «Conectar» de nuevo.

## Pantalla de consentimiento

Mientras la aplicación esté en modo **Prueba**, solo las cuentas añadidas como
«usuarios de prueba» pueden autorizarla, y el token de actualización caduca a
los siete días. Pasa la aplicación a **Producción** para tener una conexión
duradera.
