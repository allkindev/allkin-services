# Otro servicio OAuth2

La entrada comodín para un servicio que se autentica mediante OAuth2 sin figurar
en el catálogo.

## Qué hay que rellenar

- **URL de autorización** y **URL del token**: los dos puntos de entrada OAuth2
  del servicio, que da su documentación.
- **Client ID** y **Client Secret**: se obtienen registrando una aplicación en
  él.
- **Ámbitos**: separados por espacios.

## La URI de redirección

La dirección que aparece en la pestaña «Servicio» debe copiarse **tal cual** en
la configuración de la aplicación, del lado del proveedor. Es la causa casi
universal de los rechazos al conectar: un puerto distinto, una barra final de
más, y la autorización se rechaza.

## Conviene saber

Esta entrada da por supuesto el flujo «en nombre de un usuario»: un botón
«Conectar», una redirección, un regreso. Un servicio que se autentica por sí
mismo (cuenta de servicio, `client_credentials`) no se configura aquí; necesita
su propia entrada en el catálogo, como OVHcloud.
