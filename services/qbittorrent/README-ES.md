# qBittorrent

Da a un agente acceso a tu cliente BitTorrent: listar los torrents, vigilar las
velocidades de transferencia, pausar, añadir, eliminar.

## Qué necesitas

Dos cosas, ambas del propio qBittorrent:

| Campo | Dónde encontrarlo |
| --- | --- |
| URL base | La dirección de la interfaz web, **seguida de `/api/v2`** |
| Nombre de usuario, contraseña | Tools → Options → Web UI (Herramientas → Opciones → Interfaz Web) |

## La URL base

Es lo único en lo que la gente se equivoca. La dirección debe apuntar a la API,
no a la página:

```
http://127.0.0.1:8080/api/v2      ✅
http://127.0.0.1:8080             ❌ every call returns 404
```

Si qBittorrent se ejecuta en otra máquina, sustituye `127.0.0.1` por su
dirección y comprueba que «Web User Interface (Remote control)» (interfaz web de
usuario, control remoto) esté activada en las opciones; si no, nada escucha
desde fuera.

## La trampa de localhost

qBittorrent activa por defecto **«Bypass authentication for clients on
localhost»** (omitir la autenticación para los clientes en localhost).

Como resultado, si Allkin se ejecuta en la misma máquina, la conexión funciona
**incluso con una contraseña incorrecta**. La prueba se pone en verde, y no
miente: solo demuestra que la máquina es la correcta, no tus credenciales.

Esto no rompe nada. Pero el día que muevas qBittorrent a otro sitio, la conexión
fallará de golpe: la contraseña nunca se había comprobado. Desmarca la opción si
quieres que la prueba signifique algo.

## Lo que el agente puede hacer, y lo que tú validas

Leer y ajustar no necesita validación: lista de torrents, velocidades de
transferencia, pausa, reanudación, categorías, prioridades. Todo ello se deshace
con un clic.

Cinco operaciones pasan por tu validación, en la conversación:

- **añadir un torrent**: ocupa espacio en disco y ancho de banda de inmediato
- **eliminar**: con `deleteFiles=true`, los archivos descargados desaparecen del disco
- **mover los archivos de un torrent**
- **cambiar la configuración**: las preferencias incluyen la autenticación de la interfaz web
- **apagar qBittorrent**

Esto no es una indicación dada al agente: es el código el que intercepta la
llamada. Ningún agente puede saltárselo.

## Contraseña y sesión

La contraseña se usa una sola vez, para abrir la sesión. Lo que viaja después es
una cookie, renovada automáticamente y revocable desde qBittorrent sin cambiar
la contraseña. El agente no ve ni la una ni la otra.
