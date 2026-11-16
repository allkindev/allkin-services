# Google Docs

Documentos: leer su contenido, crearlos, escribir y dar formato.

## La aplicación

La misma aplicación de Google Cloud que los demás servicios Google de Allkin: **<https://console.cloud.google.com>** → un proyecto → **APIs y servicios → Credenciales → Crear credenciales → ID de cliente de OAuth**, tipo **Aplicación web**, con la URI de redirección mostrada en la pestaña «Servicio» copiada carácter por carácter. Introduce aquí su ID de cliente y su secreto, marca los ámbitos, **Conectar**.

Activa **Google Docs API** en la **Biblioteca** del mismo proyecto: un ámbito sobre una API desactivada da un rechazo que no dice por qué.

Mientras la pantalla de consentimiento esté en *Pruebas*, solo los usuarios de prueba pueden autorizar y el token muere a los siete días: pásala a *Producción* para una conexión duradera. Ver la ayuda de «Google (todas las API)» para el detalle.

## Conviene saber

La prueba de conexión no puede llamar a Docs sin un documento: el token se comprueba en «Conectar». Encontrar un documento es tarea de Google Drive: dale ambos al agente si debe buscar.
