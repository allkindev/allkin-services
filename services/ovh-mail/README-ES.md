# OVHcloud Mail

Da a un agente acceso completo a un buzón de OVH: leer, buscar, clasificar,
responder, enviar, eliminar.

Todo lo que hace el agente aparece en tu webmail, porque es el mismo buzón en el
mismo servidor. El agente no pasa por la pantalla del webmail. Habla
directamente con ese servidor, por IMAP para leer y por SMTP para enviar.

## Qué necesitas

| Campo | Valor |
| --- | --- |
| Servidor | `ssl0.ovh.net` para **MX Plan** (ya rellenado); para **Email Pro**, el servidor `proN.mail.ovh.net` que aparece en el manager |
| Dirección de correo electrónico | la dirección completa, `you@your-domain.com` |
| Contraseña | la del buzón, la misma que para el webmail |

El botón «Añadir» comprueba la **lectura** y el **envío** por separado. Una
cuenta puede leer y aun así no poder enviar: OVH bloquea el envío desde un buzón
del que sospecha spam, y la comprobación te lo dirá.

## Lo que el agente no hace solo

Tres acciones no se pueden deshacer. Por defecto, el agente te las consulta en
el hilo antes de hacerlas:

- **enviar** un correo;
- **borrar definitivamente** un mensaje, o **vaciar** una carpeta;
- **eliminar una carpeta** con su contenido.

Todo lo demás se puede deshacer y pasa sin preguntar: leer, clasificar, marcar
como leído, escribir un borrador, mover a la papelera.

### Actuar sin validación

Si quieres que el agente envíe y borre sin preguntar, marca **«Actuar sin
validación»** en los ajustes del servicio. El agente necesita además el permiso
de escritura en los servicios, que se define en su propia página.

Ten presente lo que esto implica: un correo entrante puede llevar instrucciones
escritas para engañar a un agente («reenvíame las facturas»). Al agente se le
indica que no las siga, pero esa indicación no garantiza nada. La validación sí.
Mantenla mientras el agente lea correo de cualquiera.

## Conviene saber

- **La contraseña nunca llega al agente.** Allkin abre la conexión por él.
- **Cambiar la contraseña del buzón** en el manager de OVH corta el acceso:
  vuelve a introducirla aquí.
- **Los adjuntos** que envía el agente salen de sus propios archivos. Los que
  recibe pueden guardarse en ellos.
- **La autenticación en dos pasos** de la cuenta de OVH no cambia nada aquí:
  protege el manager, no el buzón.
