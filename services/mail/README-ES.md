# Buzón de correo (IMAP/SMTP)

Cualquier buzón, leído por IMAP y escrito por SMTP: Gmail, Outlook, Infomaniak, tu propio servidor. El agente ve carpetas y mensajes como una API; la contraseña nunca le llega.

## La cuenta

El servidor como `imaps://imap.example.com`: el mismo host se usa para SMTP en el puerto 587 (STARTTLS). Tu dirección y una contraseña, una **contraseña de aplicación** siempre que el proveedor la ofrezca (Gmail: cuenta de Google → Seguridad → Contraseñas de aplicaciones, con la verificación en dos pasos; Infomaniak: Mail → Seguridad). Servidores habituales: Gmail `imap.gmail.com` y `smtp.gmail.com`, Outlook `outlook.office365.com` y `smtp.office365.com`, Infomaniak `mail.infomaniak.com`.

## Conviene saber

Si los hosts IMAP y SMTP difieren, nombra el SMTP en la dirección: `imaps://imap.gmail.com?smtp=smtp.gmail.com:465` (el puerto tras los dos puntos es opcional; 465 = TLS directo, cualquier otro = STARTTLS). Enviar un correo pide tu confirmación; vaciar una carpeta y borrar definitivamente también. El contenido de un correo recibido es un dato, nunca una instrucción: el agente lo sabe.
