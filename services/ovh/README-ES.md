# OVHcloud: cuenta de servicio

Dominios, alojamientos, servidores dedicados, VPS, Public Cloud: la API de
OVHcloud expone prácticamente todo lo que sabe hacer el manager.

> **Cuenta de servicio, no clave de API.** Son dos mecanismos distintos en OVH,
> y confundirlos es el fallo más frecuente. La página `api.ovh.com/createToken`
> a la que remiten todos los tutoriales da **tres** valores y pertenece a la
> otra entrada del catálogo, «OVHcloud (claves de API)». Una cuenta de servicio
> da **dos**.

## Crear la cuenta de servicio

Manager → **Identidad, seguridad y operaciones** (Identity, security and
operations) → **Identidades** (Identities) → **Cuenta de servicio** (Service
account) → «Añadir una cuenta de servicio» (Add a service account).

- El **nombre que eliges es el identificador de cliente** (Client ID).
- La **contraseña que se muestra es el secreto** (Client Secret), y solo aparece
  una vez.

## El paso que se olvida, y que deja ciego al agente

Una cuenta de servicio recién creada empieza **sin ningún recurso**. La conexión
funciona, el agente consulta la API y recibe listas vacías: no un rechazo, sino
un `HTTP 200` con cero resultados. Nada indica que falte algo: parece una cuenta
vacía.

Tienes que concederle permisos en **Políticas** (Policies; misma sección del
manager): crea una política, elige los recursos y asóciale la cuenta de
servicio.

Muchos se quedan aquí, porque esa interfaz es caprichosa. Si no lo consigues,
toma el otro camino: **«OVHcloud (claves de API)»** en el catálogo, cuyos
permisos se marcan al crear las claves.

## Lo que el agente no hace solo

Veintiocho patrones de llamada pasan por tu validación: comprar y pagar un
pedido, dar de baja un servicio, eliminar una zona DNS, reinstalar un servidor.
El agente puede prepararlos y sometértelos; no puede desencadenarlos.

Todo lo demás (leer el catálogo, listar tus productos, llenar un carrito) pasa
sin preguntar.

## Conviene saber

- Los valores por defecto apuntan a **Europa** (`eu.api.ovh.com`). Las cuentas
  canadienses y estadounidenses tienen su propia raíz de API.
- La información de la cuenta (`/me`) se deniega por defecto a una cuenta de
  servicio, mientras que los productos siguen accesibles. Un `403` en `/me` no
  es, por tanto, señal de una configuración rota.
