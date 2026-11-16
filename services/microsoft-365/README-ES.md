# Microsoft 365

Tu cuenta Microsoft a través de Graph: correo y calendario Outlook, OneDrive, To Do, contactos.

## La aplicación

Una aplicación registrada en Entra ID: **<https://entra.microsoft.com>** → **Registros de aplicaciones → Nuevo registro**, tipo de cuenta *personales y profesionales*, URI de redirección de tipo **Web** fijada en la dirección que Allkin muestra en esta página. Luego **Certificados y secretos → Nuevo secreto de cliente** (copia su *valor*, no su identificador). Introduce el ID de aplicación (cliente) y el secreto, marca los ámbitos que necesita el agente, y **Conectar**: Microsoft te pide autorizar.

## Conviene saber

Mantén marcado *Seguir conectado*, o la conexión muere al cabo de una hora. Enviar un correo y eliminar piden tu confirmación. Un 403 significa que un ámbito no fue concedido: vuelve a conectar con él.
