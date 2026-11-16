# Nginx Proxy Manager

Da a un agente el control de tu proxy inverso: listar los dominios publicados,
ver qué servicio atiende cada uno, diagnosticar una configuración que no carga,
publicar un servicio nuevo, pedir un certificado.

## Qué necesitas

Dos cosas, ambas del propio Nginx Proxy Manager:

| Campo | Dónde encontrarlo |
| --- | --- |
| URL base | La dirección de la interfaz de administración, **seguida de `/api`** |
| Dirección de correo electrónico, contraseña | Las que usas para iniciar sesión en esa interfaz |

## La URL base

Es lo único en lo que la gente se equivoca. La dirección debe apuntar a la API,
no a la página:

```
http://127.0.0.1:81/api      ✅
http://127.0.0.1:81          ❌ "405 Not Allowed", a web page instead of the API
```

El puerto **81** es el de la interfaz de administración; no lo confundas con los
puertos 80 y 443, por los que pasa el tráfico de los sitios que sirve el proxy.
Si Nginx Proxy Manager se ejecuta en otra máquina, sustituye `127.0.0.1` por su
dirección.

## Qué cuenta usar

La de la interfaz web. Dos observaciones:

- **La autenticación en dos pasos bloquea esta conexión.** Un intercambio
  identificador/contraseña no puede superarla: el servicio responde que espera
  un segundo factor, y Allkin te lo dirá. Usa una cuenta que no la tenga
  activada.
- **La dirección de correo de la cuenta también la usa Let's Encrypt.** Es la
  que se envía a la autoridad de certificación en cada solicitud; no hay un
  campo aparte para ello.

Puedes crear una cuenta dedicada a Allkin (Users → Add User) en lugar de
entregar la tuya: los permisos son por usuario, y un acceso de solo lectura
basta para un agente que solo tiene que vigilar.

## Lo que el agente puede hacer, y lo que tú validas

Leer no pide nada: listar hosts, certificados, listas de acceso, registro de
auditoría, informes, diagnosticar una configuración que falla.

Todo lo que cambia lo que Internet ve de la máquina pasa por tu validación, en
la conversación:

| Lo que pide el agente | Por qué necesita validación |
| --- | --- |
| Publicar o modificar un host | Un dominio pasa a ser accesible, o empieza a apuntar a otro sitio |
| Desactivar un host | El dominio deja de responder |
| Eliminar una entrada | La configuración se borra, no se desactiva: hay que rehacerla |
| Pedir un certificado | Let's Encrypt permite 5 certificados idénticos por semana |
| Eliminar un certificado | Todos los hosts que lo usan pierden HTTPS |
| Abrir un flujo TCP/UDP | Un puerto se reenvía tal cual, sin dominio ni cifrado |
| Tocar las cuentas o los ajustes | Una contraseña cambiada puede dejarte fuera |

Reactivar un host, en cambio, no pide nada: se valida lo que rompe, no lo que
repara.

Esto no es una indicación dada al agente: es el código el que intercepta la
llamada. Un agente no puede saltárselo.

Si quieres ir más lejos, la casilla **«Servicios externos en solo lectura»** de
los permisos del agente cierra toda escritura de golpe: la herramienta solo
lleva entonces los métodos que no modifican nada.

## Contraseña y sesión

La contraseña se usa una sola vez, para obtener un token. Es ese token (fechado
por Nginx Proxy Manager, renovado automáticamente cuando caduca) el que viaja
después. El agente no ve ni la una ni el otro.

## Si algo va mal

| Lo que lees | Lo que significa |
| --- | --- |
| «conexión rechazada» en la prueba | Dirección de correo o contraseña. El servicio responde `Invalid email or password` |
| «la respuesta es una página web» | Falta `/api` al final de la URL base |
| «no ha vuelto ningún campo `token`» | La cuenta usa la autenticación en dos pasos |
| «Conexión rechazada: nada escucha» | Puerto equivocado: la administración está en el 81, no en el 80 |
