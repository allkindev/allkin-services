# Home Assistant

Da a un agente el estado de tu casa, y los medios para actuar sobre ella.

## La URL base

La dirección de tu Home Assistant, **con el puerto incluido** y **sin `/api` al
final**:

```
http://192.168.1.20:8123         ✅
http://192.168.1.20:8123/api     ❌
```

## El token

Haz clic en **tu nombre, en la parte inferior de la barra lateral** → pestaña
**Seguridad** → abajo del todo, **«Crear token»**. Solo se muestra una vez.

Es un token de larga duración vinculado a tu cuenta: tiene exactamente tus
permisos. Home Assistant no sabe emitir uno más limitado; si quieres acotar lo
que puede hacer un agente, crea un usuario de Home Assistant dedicado y saca el
token de esa cuenta.

## Llamadas útiles

| Llamada | Qué hace |
| --- | --- |
| `GET /api/states` | el estado de todo |
| `GET /api/states/light.living` | el estado de una entidad |
| `POST /api/services/light/turn_on` | enciende, con `{"entity_id": "light.living"}` |

`GET /api/states` devuelve a menudo varios cientos de entidades. El agente sabe
extraer solo lo que necesita: no hace falta hacerle leerlo todo.

## Lo que ayuda de verdad a un agente

El campo **«Indicaciones para los agentes»** de la pestaña Servicio. Ninguna
documentación genérica puede saber que tu salón es `light.main_living`: a menudo
es lo único que falta para acertar a la primera.
