# YouTube

Tu canal: vídeos, listas, comentarios, suscripciones, búsqueda.

## La aplicación

La misma aplicación de Google Cloud que los demás servicios Google de Allkin: **<https://console.cloud.google.com>** → un proyecto → **APIs y servicios → Credenciales → Crear credenciales → ID de cliente de OAuth**, tipo **Aplicación web**, con la URI de redirección mostrada en la pestaña «Servicio» copiada carácter por carácter. Introduce aquí su ID de cliente y su secreto, marca los ámbitos, **Conectar**.

Activa **YouTube Data API v3** en la **Biblioteca** del mismo proyecto: un ámbito sobre una API desactivada da un rechazo que no dice por qué.

Mientras la pantalla de consentimiento esté en *Pruebas*, solo los usuarios de prueba pueden autorizar y el token muere a los siete días: pásala a *Producción* para una conexión duradera. Ver la ayuda de «Google (todas las API)» para el detalle.

## Conviene saber

La cuota diaria es de 10 000 unidades y una búsqueda cuesta 100: el agente tiene la consigna de buscar con moderación. Editar un vídeo y eliminar piden tu confirmación. Las subidas no se ofrecen por este relevo.
