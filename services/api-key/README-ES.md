# Otro servicio con clave de API

La entrada comodín: cualquier API REST que se autentique con una clave
constante.

## Qué hay que rellenar

**La URL base**: la raíz de la API, sin barra final. Las rutas que dé el agente
se añadirán a ella:

```
https://api.example.com/v1
```

**Dónde colocar la clave**: tres formas cubren casi todas las API:

| Ubicación | Qué produce | Ejemplo |
| --- | --- | --- |
| Cabecera | `Authorization: Bearer <key>` | la mayoría |
| Parámetro | `?api_key=<key>` | meteorología, indexadores |
| Ruta | la URL contiene `{secret}` | Telegram |

Los ajustes finos (nombre de la cabecera, prefijo, sufijo) sirven para formatos
poco habituales, como `X-Emby-Token: <key>` o
`Authorization: MediaBrowser Token="<key>"`.

## Lo que ayuda de verdad

El campo **«Indicaciones para los agentes»**. Un agente que se encuentra con una
API desconocida no tiene documentación: dos líneas sobre los endpoints útiles le
ahorran media docena de llamadas a tientas, y te las ahorran a ti también,
porque cada una se paga.

## Conviene saber

Si la API que quieres conectar vuelve a menudo, merece su propia entrada en el
catálogo: una carpeta en `src/services/`, un `index.ts` y este README. Entonces
aparecerá en todas partes con su logo, su ayuda y sus salvaguardas.
